<script>
  export default {
    props: ['student'],
    /*  components: {
      template: '#modal-template',
    },*/
    /*  data() {
      showModal: false
    },*/
    methods: {
      remove() {
        this.$emit('remove');
      },
    },
  };
</script>

<template lang="pug">
  div
    | {{student.firstname}} {{student.lastname}}
    button(@click="remove") Supprimer
</template>

<style>
</style>
