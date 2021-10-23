<template>
<div class="">
  <Logo/>
<div class="links">
  <nuxt-link
v-for="post in posts"
:to="{name: 'posts-id', params: {id: post.id}}"
:key="post.id"
class="button--grey">
{{ post.title}}
</nuxt-link>
</div>
</div>

</template>

<script>
import Logo from '@/components/NuxtLogo.vue';
export default {
  components: {
    Logo
  },
  
  head () {
    return {
      title: 'Home Page'
    }
  },
  computed: {
    posts () {
      return this.$store.state.posts.all
    }
  }
}
</script>
<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}

.links {
  padding-top: 15px;
}
</style>
