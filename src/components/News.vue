<template>
<div @click="callAPI">
    NEWS
    <div>
        <div v-for="element in api" :key="element">
            <p>
                <a :href="element.url">{{ element.title }}</a>
            </p>
            <p>
                {{ element.description }}
            </p>
            <img :src="element.urlToImage" class="image">
        </div>
    </div>
</div>
</template>

<script>
export default {
  data () {
    return {
      api: null
    }
  },
  name: 'Login',
  methods: {
    callAPI () {
      const url = 'https://newsapi.org/v2/top-headlines?sources=crypto-coins-news&apiKey=a53dd9c6b27444e6806d6d6d141706c1'
      fetch(url)
        .then((response) => {
          return response.json()
        })
        .then((response) => {
          this.api = response.articles
        })
    }
  }
}
</script>

<style>
.image {
  width: 25%;
}
</style>
