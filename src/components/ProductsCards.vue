<script>
export default {
    props: {
        product: {
            id: Number,
            frontImage: String,
            backImage: String,
            brand: String,
            name: String,
            price: Number,
            isInFavorites: Boolean,
        }
    }
}
</script>

<template>
    <figure class="card__image">
        <img class="image" :src="product.backImage" alt="">
        <img class="image-hover" :src="product.frontImage" alt="">
        <span class="heart-icon">&hearts;</span>
        <div class="badge-container">
            <div class="badge badge--discount">-50%</div>
            <div class="badge badge--sost">Sostenibilità</div>
        </div>
    </figure>
    <div class="card__text">
        <h3 class="brand">{{ product.brand }}</h3>
        <h3 class="product">{{ product.name }}</h3>
        <span class="price price--new">{{ product.price }}</span>
        <span class="price price--old">29,99 €</span>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card__image {
    position: relative;
}

.image-hover {
    position: absolute;
    top: 0px;
    opacity: 0;
}

.card:hover .image-hover {
    opacity: 1;
}

.heart-icon {
    line-height: 35px;
    width: 35px;
    font-size: 18px;
    text-align: center;
    background-color: white;
    position: absolute;
    right: 0;
    top: 10px;
}

.badge-container {
    position: absolute;
    bottom: 30px;
}

.badge {
    display: inline;
    width: 40px;
    font-size: 10px;
    color: white;
    padding: 5px;
}

.badge.badge--discount {
    background-color: red;
}

.badge.badge--sost {
    background-color: green;
    font-weight: bold;
}

.card__text {
    padding-top: 5px;
}

.brand {
    font-size: 10px;
    font-weight: 400;
}

.product {
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
}

.price {
    font-size: 12px;
}

.price.price--new {
    color: red;
}

.price.price--old {
    text-decoration-line: line-through;
}
</style>