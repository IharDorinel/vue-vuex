<template>
  <h3>{{ counter }}</h3>
</template>

<script>
// import { mapGetters } from 'vuex'
export default {
  computed: {
    counter() {
      return this.$store.getters['numbers/finalCounter'];
    }
    // ...mapGetters('numbers', ['finalCounter'])
  },
}
</script>