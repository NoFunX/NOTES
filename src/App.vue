<template>
  <div id="app">
    <h1> {{ title }} </h1>
    <error :error="error"/>
    <newNote @addNote="addNote" :note="note"/>
    <note :notes="notes"/>

    
    
  </div>
</template>

<script>
import error from './components/Error'
import newNote from './components/NewNote'
import note from './components/Note'



export default {
  data(){
    return {
      title: 'Твои заметки',
      error: 'поля не могут быть пустыми!',
      note: {
        title: '',
        description: '',
    },

      notes: [
        {
          title: 'Первая заметка',
          description: 'Описание заметки...',
          date: new Date(Date.now()).toLocaleDateString(),
          button:'X'
        },
        
      ]
    }
  },
  components: {
    error, newNote, note
},
  methods: {

    addNote(){
      if(this.note.title==='' || this.note.description==='') {
        this.error.style.color = 'red'
        return false
      }

      this.notes.push({
        title: this.note.title,
        description: this.note.description,
        date: new Date(Date.now()).toLocaleDateString(),
        button: 'X'
      })
      this.error=''
      this.note.title=''
      this.note.description=''
    },
    
      
    

  }
  
}
</script>

<style lang="scss">
body {
  background-color: #ebebed;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;

    h1 {
      color: #5432a8;
      font-size: 22px;
    }
}}
</style>
