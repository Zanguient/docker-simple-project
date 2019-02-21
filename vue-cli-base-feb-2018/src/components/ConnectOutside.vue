<template>
    <div>
        <h1>Call External API</h1>
        <button @click='handler'>Get Message from outside!</button>
        <p>{{ message }}</p>
    </div>
</template>

<script>
const axios = require('axios')

export default {
    data (){
        return {
            message: '',
        }
    },
    methods: {
        handler (){
            axios.get('http://localhost:3001/')
                .then((response) => {
                    console.log(response.data)
                    this.message = response.data
                })
                .catch((error) => {
                    this.message = 'Error occured.'
                })
        },
    }
}
</script>

<style>

</style>
