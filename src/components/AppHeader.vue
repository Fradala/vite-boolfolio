<template lang="">
    <header>
        <nav class="navbar navbar-expand-lg bg-body-tertiary" data-bs-theme="dark">
            <div class="container">
                <a class="navbar-brand" href="#">Boolpress</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"  data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNavDropdown">
                    <ul class="navbar-nav">
                        <li class="nav-item" v-for=" link in linkItems ">
                            <router-link :to="{name: link.routerName}" class="nav-link active">
                                {{ link.label }}
                            </router-link>
                        </li> 
                       
                       
                        
                        
                    </ul>
                </div>
            </div>
        </nav>
       
    </header>
</template>
<script>
export default {
    data(){
        return {
            linkItems: [
                {
                    label: 'Home',
                    routerName: 'home'
                },
                {
                    label: 'Projects',
                    routerName: 'projects'
                },
            ]

        }
    }
    
}
</script>
<style lang="">
    
</style>