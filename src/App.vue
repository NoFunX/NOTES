<template>
  <div id="app">
    <h1> {{ title }} </h1>
    <newNote @addNote="addNote" :note="note"/>
    <search :value="search" @search="search=$event" />
    <note :notes="notesFilter"/>



    
    
  </div>
</template>

<script>
import newNote from './components/NewNote'
import note from './components/Note'
import search from './components/Search'


export default {
  data(){
    return {
      title: 'ТВОИ ЗАМЕТКИ',
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
    newNote, note, search
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

computed: {
  notesFilter(){
    let array = this.notes
    let search = this.search
    
    if(!search) return array

    search = search.trim().toLowerCase()
    array = array.filter(function(item){
      if(item.title.toLowerCase().indexOf(search) !== -1) {
        return item
      }
    })
    
    return array
  }
}
  
}
</script>

<style lang="scss">
body {
  background-image: url("D:/mine/учеба/vue-cli/src/assets/dd110210da10519545578be3599f8445.png");
  background-size: cover;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #778ba1;
  margin-top: 15px;

    h1 {
      color: white;
      font-size: 22px;

    }
}}
</style>
