<template>
  <div class="container">
    <div>
      <p class="subtitle">
        
        simple Nuxtjs example using Animejs
        
      </p>

      <div class="links">
        <nuxt-link
          to="https://github.com/Medhanini"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </nuxt-link>
        <nuxt-link
          to="https://web.facebook.com/simo.hanini.98"
          target="_blank"
          class="button--grey"
        >
          Facebook
        </nuxt-link>
        <nuxt-link
          to="https://www.linkedin.com/in/mohamed-hanini-580a16166/"
          target="_blank"
          class="button--grey"
        >
          Linkedin
        </nuxt-link>
      </div>
      <div v-anime="{ rotate: '1turn', duration: 2000, loop: true }">
        <h2 class="test">
          mohamed hanini (test1)
        </h2>
      </div>
      <div @click.stop="next">
    <div v-show="isFirstScene" ref="first">
      スタンプを押すアニメーション用の要素を配置
    </div>

    <div v-show="isSecondScene" ref="second">
      今週のミッションを表示するアニメーション用の要素を配置
    </div>
  </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  mounted() {
         
    const targets = this.$el;
    this
      .$anime
      .timeline()
      .add({
        targets,
        translateX: 0,
        easing: 'easeOutExpo',
      })
      .add({
        targets,
        translateX: 0,
        easing: 'easeOutExpo',
      });
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.test {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 20px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
