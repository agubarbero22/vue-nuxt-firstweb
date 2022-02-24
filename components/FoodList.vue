<template>
    <div>
        <h1>{{title}}</h1>
        <ul>
            <food-item v-for="food in foods" :food="food" :key="food"> </food-item>
        </ul>
        <food-form @addFood='appendFood' :v-model="showFoodForm"> </food-form>
        <button type="submit" @click="showFoodDialog()" name="button">Add Food</button>
    </div>
</template>

<script>
    import FoodItem from './FoodItem.vue'
    import FoodForm from './FoodForm.vue'

    export default {
        name: 'FoodList',
        data() {
            return {
                showFoodForm: false,
                title: 'All Food',
                foods: [
                    {name: 'Manzana', calories: 50, fat: 1, carbs: 4, protein: 0, iron: 1},
                ],
                headers: [
                    { text: 'Dessert (100g serving)', align: 'start', sortable: false, value: 'name' },
                    { text: 'Calories', value: 'calories' },
                    { text: 'Fat (g)', value: 'fat' },
                    { text: 'Carbs (g)', value: 'carbs' },
                    { text: 'Protein (g)', value: 'protein' },
                    { text: 'Iron (%)', value: 'iron' },
                ],
            }
        },
        components: {
            FoodItem,
            FoodForm
        },

        computed:{
            show:{
                get() {
                    return this.value;
                },
                set(val) {
                    this.$emit("modified", val);
                }
            }
        },

        methods: {
            appendFood(name, calories, fat, carbs, protein, iron){
                if(
                    name == "" ||
                    calories == "" ||
                    fat == "" ||
                    carbs == "" ||
                    protein == "" ||
                    iron == ""
                ){
                    alert('Falta algún dato para añadir la comida.');
                }else{
                    this.foods.push({
                    name: name, 
                    calories: calories,
                    fat: fat,
                    carbs: carbs,
                    protein: protein,
                    iron: iron
                    })
                }
            },

            showFoodDialog(){
                this.showFoodForm = true;
            }
        }
    }
</script>

<style>
    h1 {
        text-align: center;
    }

    ul{
        text-align: center;
        list-style-type: square;
        list-style-position: outside;
    }
</style>