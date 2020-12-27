<template>
    <div class="error">
        <p class="error_p"> {{ error }}</p>
    </div>
</template>

<script>
export default {
    props: {
        error: {
            type: String,
            required: true,
        }
    }
    
}
</script>

<style lang="scss" scoped>

    .error_p {
        color: red;
    }

</style>