<template>
    <div :product="product">
        <img :src="product.image">
        <div class="prd">
            <p><strong>{{product.name}}</strong></p>
            <p>{{product.description}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'product',
        props: ['product']
    };
</script>

<style scoped>
    img {
        float: left;
        width: 300px;
    }
    .prd::after {
        clear: both;
    }
</style>     

