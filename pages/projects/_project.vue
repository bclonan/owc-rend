<template>
<!-- <main>
    <section v-if="post">
      <nav class="mb-8" aria-label="go back">
        <router-back class="block" />
      </nav>

      <article>
        <img
          v-if="post.cover"
          class="cover-image"
          :src="post.cover"
        >

        <h1 class="">{{ post.title }}</h1>
        <p class="mt-1 mb-8 text-primary-600 dark:text-primary-400">{{ post.description }}</p>
        <nuxt-content :document="post" />
        <div v-if="post.gallery" class="nuxt-content">
          <img
            v-for="image in post.gallery"
            class="image"
            :key="image.id"
            :src="image"
          >
        </div>
      </article>
    </section>
  </main> -->
<main class="h-screen bg-cover bg-center flex flex-col flex-wrap dark:text-gray-100 overflow-hidden desktopBgOne bg-white">
    <div class="relative grow w-full">
        <!---->
        <div class="w-full h-full">
            <div class="h-full w-full overflow-hidden rounded-md shadow-lg">
                <div class="absolute top-0 bottom-0 left-0 right-0 flex flex-col m-0">
                    <!-- header -->
                    <nav class="flex-none bg-white">
                        <div class="flex justify-between h-14 ">
                            <!-- tabs-->
                            <nav class="flex px-2" aria-label="Controls">
                                <button type="button" class="inline-flex items-center leading-4 py-2 text-xs px-2">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="mr-1 -ml-0.5 h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                                    </svg>
                                </button>
                                <button type="button" class="inline-flex items-center leading-4 text-black py-2 text-xs px-2">Youtube</button>
                            </nav>
                            <!-- controls -->
                            <span class="relative z-0 inline-flex pb-2">
                                <button type="button" class="relative inline-flex items-center px-2 py-2 text-sm text-black hover:bg-gray-50 focus:z-10">
                                    <span class="sr-only">Minimize</span>
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 12H6"></path>
                                    </svg>
                                </button>
                            </span>
                        </div>
                    </nav>
                    <div class="grow overflow-hidden" style="
                  background: grey;
                  ">

                        <div class="h-full flex flex-col">
                            <!-- Top nav-->
                            <!-- Bottom section -->
                            <div class="min-h-0 flex-1 flex overflow-hidden">
                                <!-- Narrow sidebar-->
                                <!-- Main area -->
                                <main class="min-w-0 flex-1 flex">
                                    <!-- Primary column -->
                                    <section aria-labelledby="primary-heading" class="min-w-0 flex-1 h-full flex flex-col overflow-y-auto order-last bg-slate-500" style="height: calc(56.25vw);
                              max-height: calc(100vh - 169px);
                              min-height: 480px;">
                                        <div id="player-theater-container" class="relative p-0 m-0 w-full h-full text-black bg-black border-0"><iframe src="https://www.youtube.com/embed/tgbNymZ7vqY" class="relative p-0 m-0 w-full text-black h-full bg-black border-0">
                                            </iframe>
                                        </div>
                                        <!-- Your content -->
                                    </section>
                                    <!-- below video content-->
                                    <div class="relative">
                                        <div class="w-full h-full bg-white"></div>
                                    </div>
                                    <!-- Secondary column (hidden on smaller screens) -->
                                </main>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!---->
    </div>
</main>
</main>
</template>

<script>
export default {
    async asyncData({
        $content,
        params,
        error
    }) {
        let post;
        try {
            post = await $content("projects", params.project).fetch();
        } catch (e) {
            error({
                message: "Project not found"
            });
        }
        return {
            post
        };
    },
}
</script>
