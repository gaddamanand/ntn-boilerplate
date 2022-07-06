<template>
  <main>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="title">About</h1>
      <posts post-type="about" :amount="10" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts
    try {
      posts = await $content('about').fetch()
    } catch (e) {
      error({ message: 'About not found' })
    }
    return { posts }
  },
}
</script>

<style>
</style>