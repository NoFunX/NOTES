<template>
  <div id="app">
    <h1> {{ title }} </h1>
    <newNote @addNote="addNote" :note="note"/>
    <note :notes="notes"/>

    
    
  </div>
</template>

<script>
import newNote from './components/NewNote'
import note from './components/Note'


export default {
  data(){
    return {
      title: 'Твои заметки',
      search: '',
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
    newNote, note
},
  methods: {

    addNote(){
      if(this.note.title==='' || this.note.description==='') {
      
        return false
      }

      this.notes.push({
        title: this.note.title,
        description: this.note.description,
        date: new Date(Date.now()).toLocaleDateString(),
        button: 'X'
      })
      this.note.title=''
      this.note.description=''
    },
},
  
}
</script>

<style lang="scss">
body {
  background-color: #e9e9f3;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #778ba1;
  margin-top: 15px;

    h1 {
      color: #4c60c5;
      font-size: 22px;

    }
}}
</style>
