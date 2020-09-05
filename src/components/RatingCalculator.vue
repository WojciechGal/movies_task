<template>
    <div>
        <b-card class="card-wrapper" header="Top Rated Movies Among Friends">
            <div class="input-label">Insert user ID:</div>
            <b-form-input v-model="input" class="id-input bottom-margin"/>
            <transition name="fade" mode="out-in">
                <b-list-group v-if="topRatedList.length" key="positive">
                    <b-list-group-item href="#" v-for="(movie, id) in topRatedList" :key="id">
                        {{id + 1}}. {{movie}}
                    </b-list-group-item>
                </b-list-group>
                <div class="card-text mt-2 table-like-margin" v-else key="negative">
                    No results found
                </div>
            </transition>
        </b-card>

    </div>
</template>

<script>
    import MoviesAnalyzer from "@/analyzers/MoviesAnalyzer";

    export default {
        name: "RatingCalculator",
        data() {
            return {
                input: ''
            }
        },
        computed: {
            topRatedList: function () {
                return MoviesAnalyzer.topRatedMoviesAmongFriends(parseInt(this.input))
            }
        }
    }
</script>

<style scoped>
    .card-wrapper {
        height: 18.5rem;
        width: 25%;
        margin-left: auto;
        margin-right: auto;
        margin-top: 12rem;
    }

    .bottom-margin {
        margin-bottom: 1rem;
    }

    .id-input {
        width: 35%;
        margin-left: auto;
        margin-right: auto;
        display: inline-block;
    }

    .input-label {
        display: inline-block;
        margin-right: 10px;
    }

    .fade-enter {
        opacity: 0;
    }

    .fade-enter-active {
        transition: opacity 1s;
    }

    .fade-leave {
        opacity: 1;
    }

    .fade-leave-active {
        transition: opacity 1s;
        opacity: 0;
    }

    .table-like-margin {
        margin-top: 4.1rem !important;
        margin-bottom: 3.6rem !important;
    }
</style>