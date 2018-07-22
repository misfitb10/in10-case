<template>
    <div class="activities__wrapper">
        <section class="activities">
            <h1 class="activities__head-title" v-if="activitiesHeading">{{activitiesHeading}}</h1>

            <p v-if="error">
                Sorry, op dit moment is er een fout opgetreden met dit onderdeel van de website. <br/>
                Voor developers: staat CORS aan?
            </p>

            <ol class="activities__list" v-if="articles.length">
                <ActivitiesListItem
                    v-for="article in articles"
                    v-bind:key="article.id"
                    v-bind:article="article"
                ></ActivitiesListItem>
            </ol>

            <a href="#" class="activities__show-all-link" v-if="showAllActivitiesButton">{{showAllActivitiesButton}}</a>
        </section>
    </div>
</template>

<script lang="ts">
    import axios from 'axios'
    import ActivitiesListItem from "./ActivitiesListItem.vue";
    import ActivitiesListItemMain from "./ActivitiesListItemMain.vue";

    export default {
        components: {ActivitiesListItem, ActivitiesListItemMain},
        data: function() {
            return  {
                articles: [],
                showAllActivitiesButton: '',
                activitiesHeading: 'Activities',
                error: false,
                apiURL: 'https://www.bilal.wtf/projects/in10-case/api/api.json'
            }
        },
        mounted() {
            axios
                .get(this.apiURL)
                .then(response => {
                    this.articles = response.data.activities.articles;
                    this.showAllActivitiesButton = response.data.activities.moreButton;
                })
                .catch(error => {
                    console.log(error);
                    this.error = true
                })
        }
    }
</script>

<style scoped lang="scss">
    @import "../../scss/base/__base";
    @import "../../scss/components/_activities";
</style>
