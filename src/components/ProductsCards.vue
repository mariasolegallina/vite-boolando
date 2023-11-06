<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="section">
        <div class="container">
            <div class="row columnrow">
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/1.webp" alt="">
                            <img class="image-hover" src="/img/1b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                            <div class="badge-container">
                                <div class="badge badge--discount">-50%</div>
                                <div class="badge badge--sost">Sostenibilità</div>
                            </div>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Levi's</h3>
                            <h3 class="product">relaxed fit tee unisex</h3>
                            <span class="price price--new">14,99 €</span>
                            <span class="price price--old">29,99 €</span>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/2.webp" alt="">
                            <img class="image-hover" src="/img/2b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                            <div class="badge-container">
                                <div class="badge badge--discount">-30%</div>
                            </div>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Guess</h3>
                            <h3 class="product">roses tee</h3>
                            <span class="price price--new">20,99 €</span>
                            <span class="price price--old">29,99 €</span>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/3.webp" alt="">
                            <img class="image-hover" src="/img/3b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                            <div class="badge-container">
                                <div class="badge badge--discount">-30%</div>
                            </div>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Come Zucchero Filato</h3>
                            <h3 class="product">voglia di colori pastello</h3>
                            <span class="price price--new">129,99 €</span>
                            <span class="price price--old">184,99 €</span>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/4.webp" alt="">
                            <img class="image-hover" src="/img/4b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                            <div class="badge-container">
                                <div class="badge badge--discount">-50%</div>
                                <div class="badge badge--sost">Sostenibilità</div>
                            </div>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Levi's</h3>
                            <h3 class="product">tee unisex</h3>
                            <span class="price price--new">14,99 €</span>
                            <span class="price price--old">29,99 €</span>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/5.webp" alt="">
                            <img class="image-hover" src="/img/5b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Maya Deluxe</h3>
                            <h3 class="product">stripe bodice</h3>
                            <span class="price price--new">99,99 €</span>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card">
                        <figure class="card__image">
                            <img class="image" src="/img/6.webp" alt="">
                            <img class="image-hover" src="/img/6b.webp" alt="">
                            <span class="heart-icon">&hearts;</span>
                            <div class="badge-container">
                                <div class="badge badge--sost">Sostenibilità</div>
                            </div>
                        </figure>
                        <div class="card__text">
                            <h3 class="brand">Esprit</h3>
                            <h3 class="product">maglione - black</h3>
                            <span class="price price--new">29,99 €</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
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