<template>
    <section class="featured">
        <ol class="featured__list">
            <li v-for="article in articles"
                class="featured__list-item">

                <img alt="featured image (todo)"
                    class="featured__image"
                    :src=article.image
                />

                <div class="featured__info">
                    <span v-if="article.dateTill.length === 0" class="featured__label featured__label--always">
                        Altijd
                    </span>

                    <span v-if="article.dateTill.length > 0" class="featured__label featured__label--now">
                        Nu
                    </span>

                    <h1 class="featured__title" v-if="article.title">{{article.title}}</h1>
                    <h2 class="featured__subtitle" v-if="article.subtitle">{{article.subtitle}}</h2>

                    <ul class="featured__artists-list" v-if="article.artists.length > 0">
                        <li class="featured__artists-list-item" v-for="artist in article.artists">{{artist}}</li>
                    </ul>

                    <div class="featured__date text--date">t/m 28 mei 2017</div>
                </div>
            </li>
        </ol>
    </section>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";
    import axios from 'axios'

    @Component({
        data: function() {
            return  {
                articles: []
            }
        },
        mounted() {
            axios
                .get('https://www.bilal.wtf/projects/in10-case/api/api.json')
                .then(response => this.articles = response.data.featured.articles)
        }
    })

    export default class Featured extends Vue {

    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_featured";
</style>
