<template>
    <form v-show="value" v-on:submit.prevent="foodSubmit(name, calories, fat, carbs, protein, iron)" class="" action="#" method="post">
        <input v-model="name" type="text" name="name" value="" placeholder="Food Name">
        <input v-model="calories" type="text" name="calories" value="" placeholder="Food Calories">
        <input v-model="fat" type="text" name="fat" value="" placeholder="Food Fat">
        <input v-model="carbs" type="text" name="carbs" value="" placeholder="Food Carbs">
        <input v-model="protein" type="text" name="protein" value="" placeholder="Food Protein">
        <input v-model="iron" type="text" name="iron" value="" placeholder="Food Iron">
        <button type="submit" name="button">Add Food</button>
    </form>
</template>

<script>
export default {
    name: 'FoodForm',
    props: {
        value: {
            type: Boolean
        },
        foods: {
            type: Array
        }
    },
    data() {
        return {
            name: '',
            calories: '',
            fat: '',
            carbs: '',
            protein: '',
            iron: ''
        }
    },
    model: {
        event: `modified`
    },

    computed: {
        show: {
            get() {
                return this.value;
            },
            set(val){
                this.$emit("modified", val);
            }
        }
    },


    methods: {
        foodSubmit(name, calories, fat, carbs, protein, iron){
            this.$emit('addFood', name, calories, fat, carbs, protein, iron);
        }
    }
}
</script>

<style>

    button{
        background: #3498db;
        background-image: -webkit-linear-gradient(top, #3498db, #2980b9);
        background-image: -moz-linear-gradient(top, #3498db, #2980b9);
        background-image: -ms-linear-gradient(top, #3498db, #2980b9);
        background-image: -o-linear-gradient(top, #3498db, #2980b9);
        background-image: linear-gradient(to bottom, #3498db, #2980b9);
        -webkit-border-radius: 5;
        -moz-border-radius: 5;
        border-radius: 5px;
        text-shadow: 1px 1px 2px #666666;
        font-family: Arial;
        color: #ffffff;
        font-size: 20px;
        padding: 10px 20px 10px 20px;
        margin: 5px;
        text-decoration: none;
    }
    button:hover{
        background: #3cb0fd;
        text-decoration: none;
    }

    input{
        background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAYAAABWKLW/AAAAFElEQVQImWNggIKysjIpHAwGBgYAWJsEdbVd/aEAAAAASUVORK5CYII=);
        background-repeat: repeat;
        background-color: #FFF;
        color: #222;
        border-width: 1px;
        border-style: solid;
        border-color: #AAA;
        text-align: center;
        border-radius: 4px;
        box-shadow: 0 0 8px -3px #888;
    }

    input:hover{
        background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAYAAABWKLW/AAAAFElEQVQImWNggIKysjIpHAwGBgYAWJsEdbVd/aEAAAAASUVORK5CYII=);
        background-repeat: repeat;
        background-color: #FFF;
        color: #222;
        border-width: 1px;
        border-style: solid;
        border-color: #4287f5;
        border-radius: 4px;
        box-shadow: 0 0 8px -3px #888;
    }
    
    input:focus{
        background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAMAAAADCAYAAABWKLW/AAAAFElEQVQImWNggIKysjIpHAwGBgYAWJsEdbVd/aEAAAAASUVORK5CYII=);
        background-repeat: repeat;
        background-color: #FFF;
        color: #222;
        border-width: 1px;
        border-style: solid;
        border-color: #AAA;
        border-radius: 4px;
        box-shadow: 0 0 8px -3px #888;
    }
</style>
