<template>
    <div class="wrapper">
        <label class= "wrapper_label">Название: </label>
        <input class = "wrapper_input" type="text" v-model="note.title">
        <span class="wrapper_span">Описание:</span>
        <textarea class = "wrapper_textarea" v-model="note.description"></textarea>
        <button @click="addNote" class = "wrapper_button">Добавить</button>
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
        width: 30%;

        .wrapper_label {
            color:#3C6A96;
            font-size: 16px;
        }
        .wrapper_input{
            display: block;
            padding: 5px 5px 5px 10px;
            margin: 5px auto;
            margin-bottom: 10px;
            border: 1px solid #3C6A96;
            width: 95%;
            font-size: 14px;
            border-radius: 5px;
            color: #3C6A96;
        }
        
        .wrapper_input:focus {
            outline: 0;
            
        }
        .wrapper_span {
            color: #3C6A96;
            margin:0px;
            font-size: 16px;
        }

    
        .wrapper_textarea{
            display: block;
            margin: 5px auto;
            padding: 5px 11px 5px 11px;
            border: 0px;
            border: 1px solid #3C6A96;
            width: 95%;
            border-radius: 5px;
            font-size: 14px;
            color: #3C6A96;
        }

        .wrapper_textarea:focus {
            outline: none;
        }

        .wrapper_button{
            font-size: 15px;
            margin: 15px auto;
            background-color: #3C6A96;
            color: white;
            padding: 10px 30px 10px 30px;
            display: block;
            border-radius: 10px;
            border: none;
            cursor: pointer;
        }

        .wrapper_button:focus {
            outline: none;
            

        }

        .wrapper_button:active {
            outline: none;
            opacity: 0.9;

        }
    }

</style>