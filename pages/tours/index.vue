<template>
  <main>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="title">Tours</h1>
      <posts post-type="tours" :amount="10" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts
    try {
      posts = await $content('tours').fetch()
    } catch (e) {
      error({ message: 'Tours not found' })
    }
    return { posts }
  },
}
</script>
