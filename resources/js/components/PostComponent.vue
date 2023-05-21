<template>
<div>

    <CreateComponent></CreateComponent>
    <IndexComponent></IndexComponent>


</div>
</template>

<script>
import IndexComponent from "./IndexComponent.vue";
import CreateComponent from "./CreateComponent.vue";
export default {
    name: "PostComponent",
    components: {
        CreateComponent,
        IndexComponent
    },
    data() {
      return {
          persons: null,
      }
    },


    methods: {

    },

    computed: {

    }
}
</script>

<style scoped>

</style>
