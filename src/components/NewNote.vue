<template>
    <div class="wrapper">
        <input class = "wrapper_input" type="text" v-model="note.title">
        <textarea class = "wrapper_textarea" v-model="note.description"></textarea>
        <button @click="addNote" class = "wrapper_button">Add Note</button>
    </div>    
</template>

<script>
export default {

    props: {
        note: {
            type: Object,
            required: true
        }
    },

    methods: {
        addNote(){
            this.$emit('addNote', this.note)
        }
    }
    
}
</script>

<style lang="scss" scoped>

    .wrapper {
        display: inline-block;
        .wrapper_input{
            display: block;
            padding: 1% 7% 1% 7%;
            margin: 0 auto;
        }

    
        .wrapper_textarea{
            display: block;
            margin: 2% auto;
            padding: 7% 11% 7% 11%;
        }

        .wrapper_button{
            margin: 4% auto;
            background-color: #5432a8;
            color: white;
            padding: 7% 15% 7% 15%;
            display: block;
            border-radius: 12%;
            border: none;

        }
    }

</style>