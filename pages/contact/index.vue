<template>
  <main>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="title">Contact</h1>
      <posts post-type="contact" :amount="10" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts
    try {
      posts = await $content('contact').fetch()
    } catch (e) {
      error({ message: 'Contact not found' })
    }
    return { posts }
  },
}
</script>

<style>
</style>