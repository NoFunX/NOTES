<template>
    <div class="search">
        <input class="search_input" type="text" placeholder="Поиск" v-model="search">
    </div>    
</template>

<script>
export default {
    props: {
        value: {
            type: String,
            required: true,
        }
    },

    data(){
        return {
            search: this.value
        }
    },

    watch: {
        search(value){
            this.$emit('search', value)
        }
    }
}
</script>

<style scoped>

    .search_input {
        color: rgb(90, 90, 90);;
        background-color: whitesmoke;
        width: 30%;
        border: 0px;
        border: 1px solid black;
        padding: 0 5px 0px 10px;
        border-radius: 5px;
        padding: 5px;
    }

    .search_input:focus {
        outline: none;
    }
</style>