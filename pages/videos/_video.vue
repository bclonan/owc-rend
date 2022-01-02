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
        https://www.youtube.com/embed/dfvZ5wveUow
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

<div class="h-screen bg-cover bg-center flex flex-col flex-wrap dark:text-gray-100 overflow-hidden desktopBgOne bg-white">
    <div class="relative grow w-full" v-if="post">
        <!---->
        <div class="w-full h-full">
            <div class="h-full w-full ">
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
                    <div class="grow">
                        <!-- sidebar -->
                        <!-- <ExplorerSideBar /> -->
                        <!-- content-->
                        <!-- <ExplorerContent /> -->
                        <div class="h-full flex flex-col">
                            <!-- Top nav-->
                            <!-- Bottom section -->
                            <div class="min-h-0 flex-1 flex ">
                                <!-- Narrow sidebar-->
                                <!-- Main area -->
                                <main class="min-w-0 flex-1 flex flex-wrap flex-col">
                                    <!-- Primary column -->
                                    <section aria-labelledby="primary-heading" class="min-w-0 flex-1 h-full flex flex-col  " style="height: calc(56.25vw);
                              max-height: calc(100vh - 169px);
                              min-height: 480px;">
                                        <div id="player-theater-container" class="relative p-0 m-0 w-full h-full text-black bg-black border-0" v-if="post.url"><iframe :src="post.url" class="relative p-0 m-0 w-full text-black h-full bg-black border-0">
                                            </iframe>
                                        </div>
                                        <!-- Your content -->
                                    </section>
                                    <!-- below video content-->
                                    <div class="relative ">
                                        <div class="w-full h-full bg-white">
                                            <div class="bg-white ">
                                                <div class="px-4 py-5 sm:px-6 ">
                                                    <h3 class="text-lg leading-6 font-medium text-gray-900">
                                                        Applicant Information
                                                    </h3>
                                                    <div class="flex justify-between h-8">
                                                        <p class="mt-1 max-w-2xl text-sm text-gray-500">1 billion views - Mar 9, 2021</p>
                                                        <span class="relative z-0 inline-flex pb-2  my-2 ">
                                                            <button type="button" class="relative inline-flex items-center px-2 py-2 text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 font-bold">
                                                                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5" />
                                                                </svg>
                                                                <span>109k</span>
                                                            </button>
                                                            <button type="button" class="relative uppercase inline-flex items-center px-2 py-2 text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 font-bold">
                                                                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14H5.236a2 2 0 01-1.789-2.894l3.5-7A2 2 0 018.736 3h4.018a2 2 0 01.485.06l3.76.94m-7 10v5a2 2 0 002 2h.096c.5 0 .905-.405.905-.904 0-.715.211-1.413.608-2.008L17 13V4m-7 10h2m5-10h2a2 2 0 012 2v6a2 2 0 01-2 2h-2.5" />
                                                                </svg>
                                                                <span>DISLIKE</span>
                                                            </button>
                                                            <button type="button" class="relative uppercase inline-flex items-center px-2 py-2 text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 font-bold">
                                                                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" />
                                                                </svg>
                                                                <span>share</span>
                                                            </button>
                                                            <button type="button" class="relative uppercase inline-flex items-center px-2 py-2 text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 font-bold">
                                                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                                                    <path fill-rule="evenodd" d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd" />
                                                                </svg>
                                                                <span>download</span>
                                                            </button>
                                                            <button type="button" class="relative uppercase inline-flex items-center px-2 py-2 text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 font-bold">
                                                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                                                    <path d="M5 4a2 2 0 012-2h6a2 2 0 012 2v14l-5-2.5L5 18V4z" />
                                                                </svg>
                                                                <span>save</span>
                                                            </button>
                                                        </span>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                        <!-- desc area -->
                                        <div class="w-full">
                                        </div>
                                    </div>
                                    <!-- desk area -->
                                    <div>
                                        <div class="border-b border-gray-200 border-t mx-6"></div>
                                        <div class="flex text-sm text-gray-500 space-x-4 bg-white px-6">
                                            <div class="flex-none py-10">
                                                <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&amp;auto=format&amp;fit=facearea&amp;facepad=8&amp;w=256&amp;h=256&amp;q=80" alt="" class="w-10 h-10 bg-gray-100 rounded-full">
                                            </div>
                                            <div class="flex-1 py-10 ">
                                                <div class="flex w-full  justify-between">
                                                    <div>
                                                        <h3 class="font-medium text-gray-900">John Snow</h3>
                                                        <p class="text-xs">1.7m subscribers</p>
                                                    </div>
                                                    <button class="bg-red-600 text-white px-2 uppercase font-semibold"> Subscribe</button>
                                                </div>
                                                <div class="mt-4 prose prose-sm max-w-none text-gray-500">
                                                    <p>{{ post.description }}</p>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <!-- comment area-->
                                    <div>
                                        <div class="border-b border-gray-200 border-t mx-6"></div>
                                        <div class="flex text-sm text-gray-500 space-x-4 bg-white px-6 over">
                                            <div class="flex-none py-10">
                                                <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&amp;auto=format&amp;fit=facearea&amp;facepad=8&amp;w=256&amp;h=256&amp;q=80" alt="" class="w-10 h-10 bg-gray-100 rounded-full">
                                            </div>
                                            <div class="flex-1 py-10 ">
                                                <div class="flex w-full  justify-between">
                                                    <div class="flex items-center justify-center space-x-2">
                                                        <h3 class="font-medium text-gray-900 text-xs">Hector Gibbons</h3>
                                                        <p class="text-xs">8 months ago</p>
                                                    </div>
                                                </div>
                                                <div class="mt-1 prose prose-sm max-w-none text-gray-500">
                                                    <p>Lorem lorem lorem lorem</p>
                                                </div>
                                                <div class="  text-gray-500">
                                                    <span class="relative z-0 inline-flex text-xs  space-x-1">
                                                        <button type="button" class="relative inline-flex items-center  text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 "><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-6 w-6">
                                                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"></path>
                                                            </svg> <span>109k</span></button>
                                                        <button type="button" class="relative inline-flex items-center  text-sm text-gray-700 hover:bg-gray-50 focus:z-10 space-x-1 "><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-6 w-6">
                                                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14H5.236a2 2 0 01-1.789-2.894l3.5-7A2 2 0 018.736 3h4.018a2 2 0 01.485.06l3.76.94m-7 10v5a2 2 0 002 2h.096c.5 0 .905-.405.905-.904 0-.715.211-1.413.608-2.008L17 13V4m-7 10h2m5-10h2a2 2 0 012 2v6a2 2 0 01-2 2h-2.5"></path>
                                                            </svg> <span>5</span></button>
                                                        <button type="button" class="pl-3 relative uppercase inline-flex
                                                            items-center  text-sm text-gray-700
                                                            hover:bg-gray-50 focus:z-10 space-x-1 "><span>Reply</span></button> </span>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </main>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    layout: 'ytlayout',
    async asyncData({
        $content,
        params,
        error
    }) {
        let post;
        try {
            post = await $content("videos", params.project).fetch();
        } catch (e) {
            error({
                message: "Video not found"
            });
        }
        return {
            post
        };
    },
}
</script>
