<template>
    <div class="w-25">
        <input type="text" class="form-control mb-2" v-model="name" id="name" placeholder="name">
        <input type="number" class="form-control mb-2" v-model="age" id="age" placeholder="age">
        <input type="text" class="form-control mb-2" v-model="job" id="job" placeholder="job    ">
        <button @click.prevent="addPerson"  class="btn btn-primary" >Добавить</button>

        <SomeComponent :obj="obj"></SomeComponent>
    </div>
</template>

<script>
import SomeComponent from './SomeComponent.vue'

export default {
    name: "CreateComponent",
    components: {SomeComponent},

    data() {
        return {
            name:null,
            age:null,
            job:null,
            obj: {
                color: 'yellow',
                number: 5,
                isPublished: false
            }
        }
    },

    mounted() {
        this.$parent.$refs.index.indexLog();
    },

    methods: {
        addPerson() {
            axios.post('/api/people', {name: this.name, age: this.age, job:this.job})
                .then( res => {
                    this.name = null;
                    this.age = null;
                    this.job = null;

                    this.$parent.$refs.index.getPeople();
                })
        }
    },
}
</script>

<style scoped>

</style>
