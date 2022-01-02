<template>
<div class="relative">
 <div class="w-full md:flex">
        <div class="md:w-1/2 md:flex-1 md:flex md:justify-center md:items-center md:order-2">
            <div class="text-center w-10/12 max-w-screen-lg m-auto my-8 md:ml-12">
                <h2 class="text-xl uppercase mb-4 md:text-2xl">Heading Lorem Ipsum</h2>
                <p class="mb-8">{{imageGridText}}</p>
                <a href="#" class="bg-gray-300 px-12 py-2 hover:bg-gray-200">
                CTA s
                </a>
            </div>
        </div>
        <div class="md:w-1/2 md:flex-1">
            <img :src="imgUrl" class="w-full md:object-cover md:h-full" alt="" />
        </div>
    </div>
    </div>

    </div>
</template>

<script>
export default {
  props: {
    imgUrl: {
      type: String,
      default : 'https://via.placeholder.com/150'
    }
  },
  data() {
    return {
      imageGridText: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.`
    }
  },
}
</script>