<template>
  <!-- <NuxtContent
    class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl mx-auto"
    :document="post"
  /> -->
  <main class="prose prose-sm sm:prose lg:prose-lg xl:prose-xl mx-auto  dark:prose-invert">

    <article v-if="post">
        <h1>{{ post.title }}</h1>
        <NuxtContent  :document="post" />
    </article>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
      post = await $content("blog", params.blog).fetch();
    } catch (e) {
      error({ message: "Post not found" });
    }
    return { post };
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    }
  }
}
</script>
