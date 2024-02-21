<template lang="">
    <div>
        <img :src="image" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>
            <p>
                {{ author }}
            </p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>
    
    
</template>
<script>
export default {
    data(){
        return {

        }
    },
    props:{
       title:{
            required: true,
            type: String
        },
       image:{
            required: true,
            type: String
        },
        author:{
            required: true,
            type: String
        },   
    }
    
}
</script>
<style lang="">
    
</style>