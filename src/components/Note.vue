<template>
    <div class="wrapper">
        <div class="notes">
            <div @click="clickNote()" class="note" v-for="(note, index) in notes" :key="index">
                <div class="header">
                <span class="header_title"> {{ note.title }}</span>
                <button @click="removeNote(index)" class="header_delete"> {{ note.button }} </button>
                </div>
                <p class="note_description"> {{ note.description }}</p>
                <span class="note_date"> {{ note.date }} </span>
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
        },

        clickNote($event){
            $event.style.width="100%"
        }
    }
    
}
</script>

<style lang="scss" scoped>
    .notes{
        margin: 40px auto;
        border: 0px;
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        padding: 0;
        .note {
            width: 30%;
            margin-bottom: 20px;
            margin-left: 1.5%;
            margin-right: 1.5%;
            border: 1px solid #74A2CF;
            border-bottom-left-radius: 10px;
            border-bottom-right-radius: 10px;
            box-shadow: 0 3px 10px #74A2CF;
            cursor: pointer;

            .header {
                display: flex;
                align-items: center;
                justify-content: space-between;
            

                .header_title {
                    font-size: 20px;
                    margin: 5px;
                    color:  #3C6A96;
                    text-align: left;
                    

}

                .header_delete {
                border: 0px;
                color: black;
                cursor: pointer;
                background: white;
            }

            .header_delete:active {
                outline: none;
            } 
            }

            .note_description {
                margin: 5px;
                color:  black;
                text-align: left;
                display: block;
                font-size: 14px;
                border-radius: 5px;
                padding: 5px;
            }

            .note_date {
                display: block;
                text-align: right;
                margin-right: 5px;
                margin-bottom: 5px;
                font-size: 12px;
                color:#3C6A96;
                margin-top: 9px;
                

            }

    }
    }


</style>