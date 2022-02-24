<template>
    <li>
        {{food.name}} - {{food.calories}} - {{food.fat}} - {{food.carbs}} - {{food.protein}} - {{food.iron}}
    </li>
</template>

<script>
export default {
    name: 'FoodItem',
    props: ['food']
}
</script>

<style>
    li {
        display: block;
        margin: 0, 10px;
        padding: 2px;
    }
</style>