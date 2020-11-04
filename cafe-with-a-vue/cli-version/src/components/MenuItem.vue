<template>
<div>
    <img
    class="menu-item__image"
    :src="imgSrc"
    :alt="imgAlt"
    />
    <div>
        <h3>{{ name }}</h3>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <div>
            <label for="add-item-quantity"
            >Quantity: {{ quantity }}</label
            >
            <input
            v-model.number="quantity"
            id="add-item-quantity"
            type="number"
            />
            <button @click="addToShoppingCart(quantity)">
            Add to Shopping Cart
            </button>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'MenuItem',
    props:[ 'addToShoppingCart', 'imgSrc', 'imgAlt', 'name', 'inStock', 'quantity']
}
</script>
