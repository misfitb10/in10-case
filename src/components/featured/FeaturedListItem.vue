<template>
    <li class="featured__list-item">
        <img :src=article.image
             alt="featured image (todo)"
             class="featured__image"
        />

        <div class="featured__info">
            <span v-if="article.dateTill.length === 0" class="featured__label featured__label--always">
                Altijd
            </span>

            <span v-else class="featured__label featured__label--now">
                Nu
            </span>

            <h1 v-if="article.title" class="featured__title">{{article.title}}</h1>
            <h2 v-if="article.subtitle" class="featured__subtitle">{{article.subtitle}}</h2>

            <ul v-if="article.artists.length > 0" class="featured__artists-list">
                <li v-for="artist in article.artists" class="featured__artists-list-item">{{artist}}</li>
            </ul>

            <div v-if="article.dateTill.length > 0" class="featured__date text--date">{{article.dateTill}}</div>
        </div>
    </li>
</template>

<script lang="ts">
    export default {
        props: ['article']
    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_featured";
</style>
