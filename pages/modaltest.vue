<template>
  <div class="section">
    <modal>hello</modal>
    <button @click="show">show modal</button>
  </div>
</template>

<script>

  import Modal from "../components/modal";

  export default {
    components: {Modal},
    data() {
      return {

      }
    },
    methods: {
      show(){
        this.$store.dispatch('toggleModal');
      }
    },
    computed: {

    },
    created() {

    }
  }
</script>
<style>
</style>
