<template>

    <food-list> </food-list>

</template>

<script>
import FoodList from '../components/FoodList.vue';
  export default {
  components: { FoodList },
  
    name: 'MyForm',
    data(){
      return {

      }
    },
    methods: {
      remove(){
        this.$emit('remove');
      },
    }
  }
</script>
