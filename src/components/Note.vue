<template>
    <div class="wrapper">
        <div class="notes">
            <div class="note" v-for="(note, index) in notes" :key="index">
                <h4 class="note_title"> {{ note.title }}</h4>
                <p class="note_description"> {{ note.description }}</p>
                <span class="note_date"> {{ note.date }} </span>
                <button @click="removeNote(index)" class="note_delete"> {{ note.button }} </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        notes:{
            type: Array,
            required: true,
        }
    },

    methods: {
        removeNote(index) {
           this.notes.splice(index, 1)
        }
    }
    
}
</script>

<style lang="scss" scoped>
    .notes{
        margin: 0 auto;
        border: 0px;
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        .note {
            display: inline-block;
            margin-left: 10%;
            .note_delete {
                border: 0px;
                color: white;
            }

    }
    }


</style>