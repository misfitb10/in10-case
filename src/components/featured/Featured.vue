<template>
    <section class="featured">
        <p v-if="error">
            Sorry, op dit moment is er een fout opgetreden met dit onderdeel van de website. <br/>
            Voor developers: staat CORS aan?
        </p>

        <ol class="featured__list" v-if="articles.length">
            <FeaturedListItem
                v-for="article in articles"
                v-bind:key="article.id"
                v-bind:article="article"
            ></FeaturedListItem>
        </ol>
    </section>
</template>

<script lang="ts">
    import axios from 'axios'
    import FeaturedListItem from "./FeaturedListItem.vue"

    export default {
        components: {FeaturedListItem},
        data: function() {
            return  {
                error: false,
                articles: [],
                apiURL: 'https://www.bilal.wtf/projects/in10-case/api/api.json'
            }
        },
        mounted() {
            axios
                .get(this.apiURL)
                .then(response => this.articles = response.data.featured.articles)
                .catch(error => {
                    console.log(error);
                    this.error = true
                })
        }
    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_featured";
</style>
