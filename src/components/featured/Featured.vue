<template>
    <section class="featured">
        <ol class="featured__list">
            <li class="featured__list-item">
                <img class="featured__image" alt="Vaste collectie" src="/assets/images/vaste-collectie.png"/>

                <div class="featured__text">
                    <span class="featured__label featured__label--always">Altijd te zien</span>
                    <div class="featured__info">
                        <h1 class="featured__title">Vaste Collectie</h1>
                        <h2 class="featured__subtitle">Reis door de kunstgeschiedenis</h2>
                    </div>
                </div>
            </li>

            <li class="featured__list-item">
                <img class="featured__image" alt="Gek op surrealisme" src="/assets/images/gek-op-surrealisme.png"/>

                <div class="featured__text">
                    <span class="featured__label featured__label--now">Nu te zien</span>
                    <div class="featured__info">
                        <h1 class="featured__title">Gek op surrealisme</h1>
                        <ul class="featured__artists-list">
                            <li class="featured__artists-list-item">Dali</li>
                            <li class="featured__artists-list-item">Ernst</li>
                            <li class="featured__artists-list-item">Magritte</li>
                            <li class="featured__artists-list-item">Miro</li>
                        </ul>
                        <div class="featured__date text--date">t/m 28 mei 2017</div>
                    </div>
                </div>
            </li>
        </ol>
    </section>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";

    @Component
    export default class Featured extends Vue {

    }
</script>

<style scoped lang="scss">

</style>
