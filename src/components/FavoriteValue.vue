<template>
  <h3>{{ counter }}</h3>
  <p>We do more...</p>
</template>

<script>
// import { mapGetters } from 'vuex'
export default {
  computed: {
    counter() {
      return this.$store.getters['numbers/normalizedCounter'];
    }
    // ...mapGetters('numbers',['normalizedCounter'])
  },
}
</script>