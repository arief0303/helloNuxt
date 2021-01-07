<template>
    <div>
        <h2>This is user's id {{$route.params.id}}</h2>
    </div>
</template>

<script>
export default {
    data() {
    return {
      title: "userID"
    };
  },

  head() {
    return {
      title: this.title,
    };
  },

    validate(context) {
        return /^\d+$/.test(context.params.id)
    }
}
</script>