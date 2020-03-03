<template>
  <div class="container">
    <div>

      <h2 class="title">
        Welcome to the best dad jokes on the web!
      </h2>
      <h2 class="subtitle">
        List of bad dad jokes to learn Nuxt (no Joke!)
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  head(){
      return {
          title:'Welcome to dad jokes',
          meta: [
              {
                  hid:'description',
                  name: 'description',
                  content: 'Welcome to dad jokes - List of bad dad jokes to learn Nuxt (no Joke!)'
              }
          ]
      }
  }
}
</script>

<style>

</style>
