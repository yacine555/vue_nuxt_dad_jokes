<template>
  <div>
      <SearchJokes v-on:search-text="searchText"/>
      <Joke v-for="joke in jokes" v-bind:key="joke.id" v-bind:id="joke.id" v-bind:joke="joke.joke"></Joke>
  </div>
</template>

<script>
import axios from "axios";
import Joke from '~/components/Joke';
import SearchJokes from '~/components/SearchJokes';

export default {
    components: {
        Joke,
        SearchJokes
    },
    data() {
        return {
            jokes: []
        };
    },
    async created() {
        const config = {
            headers:{
                'Accept': 'application/json'
            }
        };
        try {
            const res = await axios.get('https://icanhazdadjoke.com/search',config);
            this.jokes = res.data.results;
        } catch (error) {
            console.log(err);
        }
    },
    methods: {
        async  searchText(text){
            const config = {
                headers:{
                    'Accept': 'application/json'
                }
            };
            try {
                const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config);
                this.jokes = res.data.results;
            } catch (error) {
                console.log(err);
            }
        }
    },
    head() {
        return {
            title:'Dad jokes',
            meta: [
                {
                    hid:'description',
                    name: 'description',
                    content: 'Dad jokes'
                }
            ]
        }
    }
};
</script>

<style>

</style>