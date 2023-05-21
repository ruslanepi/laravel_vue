<template>
<div>

    <CreateComponent></CreateComponent>
    <IndexComponent ref="index"></IndexComponent>


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

    mounted() {

    },

    methods: {
        parentLog() {
            console.log('this is parent component');
        }
    },

    computed: {

    }
}
</script>

<style scoped>

</style>
