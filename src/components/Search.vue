<template>
    <div class="search">
        <input class="search_input" type="text" placeholder="Поиск по заметкам" v-model="search">
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
        color: #3C6A96;
        background-color: white;
        width: 30%;
        border: 0px;
        border-bottom: 1px solid #3C6A96;
        padding: 0 5px 0px 10px;
    }

    .search_input:focus {
        outline: none;
    }
</style>