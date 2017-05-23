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
    | {{student.first_name}} {{student.name}} {{ student.age }}
    button(@click="remove") Supprimer
</template>

<style>
</style>
