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
      title: 'Your Notes',
      error: null,
      note: {
        title: 'Title',
        description: 'Description',
    },

      notes: [
        {
          title: '',
          description: '',
          date: '',
          button: ''
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
        this.error = 'fields cant be blank!'
        return false
      }

      this.notes.push({
        title: this.note.title,
        description: this.note.description,
        date: new Date(Date.now()).toLocaleDateString(),
        button: '❌'
      })
      this.error=''
      this.note.title=''
      this.note.description=''
    },

  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
