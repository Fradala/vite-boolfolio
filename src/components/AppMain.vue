<template lang="">
    <main class="container">
        <section class=row>
            <div class="col-12">
                <h1>
                    I miei progetti:
                </h1>
            </div>

        </section>
        
    </main>
</template>
<script>
import axios from 'axios';

export default {
    name: 'AppMain',

    data() {

    },

    methods:{
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects', {
                params: {
                
                }
            })
            .then(function (response) {
                console.log(response);
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