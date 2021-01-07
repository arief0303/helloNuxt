<template>
<div>
<h1>Hello users</h1>
<h6>Regex only accepts numerals, no letters allowed.</h6>
<input type="text" v-model="id">
<button @click="loadUser">Load user</button>
</div>
</template>

<script>
export default {
    data() {
        return {
            id: ''
        }
    },

    methods: {
        loadUser() {
            this.$router.push(`/users/${this.id}`)
        }
    }
}
</script>