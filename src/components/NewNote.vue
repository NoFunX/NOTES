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
            color:white;
            font-size: 16px;
        }
        .wrapper_input{
            background: white;
            display: block;
            padding: 5px 5px 5px 10px;
            margin: 5px auto;
            margin-bottom: 10px;
            border: 1px solid black;
            width: 95%;
            font-size: 14px;
            border-radius: 5px;
            color: rgb(90, 90, 90);;
        }
        
        .wrapper_input:focus {
            outline: 0;
            
        }
        .wrapper_span {
            color: rgb(255, 255, 255);
            margin:0px;
            font-size: 16px;
        }

    
        .wrapper_textarea{
            display: block;
            margin: 5px auto;
            padding: 5px 11px 5px 11px;
            border: 0px;
            border: 1px solid black;
            width: 93%;
            border-radius: 5px;
            font-size: 14px;
            color: rgb(90, 90, 90);;
            background: white;
        }

        .wrapper_textarea:focus {
            outline: none;
        }

        .wrapper_button{
            font-size: 15px;
            margin: 15px auto;
            background-color: #fb0000;
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