<template>

<main >
 <div v-if="posts" class="h-screen bg-cover bg-center flex flex-col flex-wrap dark:text-gray-100 overflow-hidden desktopBgOne bg-white">
   <div class="relative grow w-full">
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

                  <div class="h-full flex flex-col bg-gray-50">
                     <!-- Top nav-->
                     <!-- Bottom section -->
                     <div class="min-h-0 flex-1 flex ">
                        <!-- Narrow sidebar-->
                        <!-- Main area -->
                        <main class="min-w-0 flex-1 flex flex-wrap flex-col">
                           <!-- video section -->
                           <div class="bg-gray-50">
                              <div class="max-w-2xl mx-auto py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
                                 <div class="md:flex md:items-center md:justify-between">
                                    <h2 class="text-2xl  tracking-tight text-gray-700">Videos</h2>
                                 </div>
                                 <videos post-type="videos" :amount="60" />
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
</main>
</template>

<script>
export default {
  layout: 'ytlayout',
  async asyncData({ $content, error }) {
    let posts;
    try {
      posts = await $content("videos").fetch();
    } catch (e) {
      error({ message: "videos not found" });
    }
    return { posts };
  },
}
</script>
