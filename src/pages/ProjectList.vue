<template lang="">
    <main class="container">
        <section class="row justify-content-center">
            <div class="col-12">
                <h1 class="mt-4 mb-4">
                    Projects
                </h1>
            </div>
            <div class="card p-0 col-3 me-4" v-for="project in projects" :key="project.id" >
                <img :src="project.image" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ project.name_project }}</h5>
                    <p>
                        {{ project.author }}
                    </p>
                    <a href="#" class="btn btn-primary">Go somewhere</a>
                </div>
            </div>

        </section>

    </main>
</template>
<script>
import axios from 'axios';

export default {
    name: 'AppMain',

    data() {
        return {
            projects:[],
        }
    },

    methods:{
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects', {
                params: {
                
                }
            })
            .then((response)=> {
                console.log(response.data.result.data);
                this.projects = response.data.result.data;
            })
            .catch(function (error) {
                console.warn(error);
            })
            
        }
    },

    created() {
        this.getProjects();
    },
    
}
</script>
<style lang="">
    
</style>