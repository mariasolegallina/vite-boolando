<script>
import { store } from '../store'

export default {
    props: {
        product: Object
    },
    data() {
        return {
            store: store,
        }
    },
    methods: {
        //   onClick() {
        //     // console.log(this.item.titolo)
        //     // this.item = {} NON POSSIAMO FARLO
        //     console.log(this.cottura)
        //   },
    },

}

</script>

<template>
    <div class="card">
        <figure class="card__image">
            <img class="image" :src="`/img/${product.frontImage}`" alt="">
            <img class="image-hover" :src="`/img/${product.backImage}`" alt="">
            <span class="heart-icon">&hearts;</span>
            <div class="badge-container">
                <div v-for="(badge) in  product.badges " class="badge badge--discount"
                    :class="badge.value === 'Sostenibilità' ? 'badge--sost' : ''">
                    {{ badge.value }}
                </div>
            </div>
        </figure>
        <div class="card__text">
            <h3 class="brand">{{ product.brand }}</h3>
            <h3 @click="$emit('show')" class="product">{{ product.name }}</h3>
            <span class="price" v-for="badge in product.badges" :class="badge.type === 'discount' ? 'price--old' : ''">
                {{ product.price }}</span>
            <!-- <span class="price price--old">29,99 €</span> -->
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card__image {
    position: relative;

    .image-hover {
        position: absolute;
        top: 0px;
        opacity: 0;
    }

    &:hover .image-hover {
        opacity: 1;
    }
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

    &.badge--discount {
        background-color: $discount;
        margin-right: 4px;
    }

    &.badge--sost {
        background-color: $sustainability;
        font-weight: bold;
    }

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
    margin-right: 4px;


    &.price.price--new {
        color: $discount;
    }

    &.price.price--old {
        text-decoration-line: line-through;
        color: $discount;
    }

}
</style>