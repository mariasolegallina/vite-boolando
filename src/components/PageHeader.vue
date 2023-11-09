<script>
export default {
    data() {
        return {
            logo: '/img/boolean-logo.png',
            menu: [
                'Donna',
                'Uomo',
                'Bambini',
            ],
            icone: [],
        }
    }
}
</script>

<template>
    <header>
        <div class="container">
            <div class="row justify-between align-center">
                <div class="col">
                    <ul class="nav-menu">
                        <li class="nav-menu__item" v-for="(item, i) in menu"><a href="#">{{ item }}</a></li>
                    </ul>
                </div>
                <div class="col logo">
                    <img src="/img/boolean-logo.png" alt="logo bianco boolean">
                </div>
                <div class="col">
                    <div class="header-icons"></div>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

header {
    background-color: $main-orange;
    color: white;
}

.nav-menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.nav-menu__item>a {
    display: block;
    padding-right: 10px;
    line-height: 40px;
    font-size: 12px;
    font-weight: bold;
}

.logo {
    max-width: 110px;
    padding: 12px 0;
}
</style>