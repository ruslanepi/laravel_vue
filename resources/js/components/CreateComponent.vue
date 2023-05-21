<template>
    <div class="w-25">
        <input type="text" class="form-control mb-2" v-model="name" id="name" placeholder="name">
        <input type="number" class="form-control mb-2" v-model="age" id="age" placeholder="age">
        <input type="text" class="form-control mb-2" v-model="job" id="job" placeholder="job">
        <button @click.prevent="addPerson"  class="btn btn-primary" >Добавить</button>
    </div>
</template>

<script>
export default {
    name: "CreateComponent",

    data() {
        return {
            name:null,
            age:null,
            job:null,
        }
    },

    methods: {
        addPerson() {
            axios.post('/api/people', {name: this.name, age: this.age, job:this.job})
                .then( res => {
                    this.name = null;
                    this.age = null;
                    this.job = null;
                })
        }
    },
}
</script>

<style scoped>

</style>
