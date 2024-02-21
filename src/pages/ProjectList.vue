<template lang="">
    <main class="container">
        <section class="row justify-content-center">
            <div class="col-12">
                <h1 class="mt-4 mb-4">
                    Projects
                </h1>
            </div>
            
            <SingleCard class="card p-0 col-3 me-4" v-for="project in projects" :key="project.id"
                :title="project.name_project" :image="project.image" :author="project.author"
            />
            

        </section>

    </main>
</template>
<script>
import SingleCard from '@/components/SingleCard.vue';
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
    components:{
        SingleCard
    },

    created() {
        this.getProjects();
    },
    
}
</script>
<style lang="">
    
</style>