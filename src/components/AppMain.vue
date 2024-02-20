<template lang="">
    <main class="container">
        <section class=row>
            <div class="col-12">
                <h1>
                    I miei progetti:
                </h1>
                <ul>
                    <li v-for="project in projects" :key="project.id">
                        {{ project.name_project }}
                    </li>
                </ul>
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