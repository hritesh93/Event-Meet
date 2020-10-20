<template>
  <div>
    <h1>Create an event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p>There are {{ catLength }} categories</p>
    <p>{{ getEventById(2) }}</p>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  computed: {
    catLength() {
      return this.$store.getters.catLength
    },
    ...mapGetters(['getEventById']),
    // eslint-disable-next-line prettier/prettier
    ...mapState(['user', 'categories']),
    // eslint-disable-next-line prettier/prettier
  },
}
</script>

<style scoped>
</style>
