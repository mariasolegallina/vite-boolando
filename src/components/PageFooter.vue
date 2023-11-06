<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <footer>
        <div class="container">
            <div class="row justify-between">
                <div class="col">
                    <h4 class="footer-title">Boolando s.r.l.</h4>
                    <ul class="footer-menu">
                        <li class="footer-menu__item"><a href="#">Informazioni legali</a></li>
                        <li class="footer-menu__item"><a href="#">Informativa sulla privacy</a></li>
                        <li class="footer-menu__item"><a href="#">Diritto di recesso</a></li>
                    </ul>
                </div>
                <div class="col">
                    <h5 class="footer-title">Trovaci anche su</h5>
                    <ul class="footer-icon">
                        <li></li>
                        <li></li>
                        <li></li>
                        <li></li>
                        <li></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

footer {
    background-color: #1a1a1a;
    padding: 20px 0;
    color: white;
}

.footer-menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.footer-title {
    font-size: 12px;
    font-weight: bold;
    line-height: 20px;
}

.footer-menu__item {
    display: block;
    padding-right: 10px;
    line-height: 25px;
    font-size: 10px;
}
</style>