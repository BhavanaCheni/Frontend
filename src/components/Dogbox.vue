<template>
    
    <div class="breed">
        
        <div v-for="dog in dogs" :key="dog.id" >
            <Dog :dog="dog"/>
     
               
                
                
        
        </div>
       
    </div>

</template>

<script>

import Dog from './Dog.vue'
export default{

    name: 'Dogbox',
    components: {
        Dog
    },
    props: {
        dogs: Array
    }
}

</script>

<style scoped>

.breed{

    background-color:#14213d;
    padding: 1em;
    color: rgb(243, 129, 227);
}

</style>
