<template>
<div class="mt-6 grid grid-cols-2 gap-x-4 gap-y-10 sm:gap-x-6 md:grid-cols-4 md:gap-y-0 lg:gap-x-8" v-if="posts.length > 0">
    <!-- single video-->

    <div class="group relative" v-for="(post, index) in posts" :key="index">

            <div class="w-64 h-56 bg-gray-200  overflow-hidden group-hover:opacity-75  aspect-square">
                <img v-if="post.cover" class="w-full h-full object-center object-cover aspect-square" :src="post.cover">

            </div>
            <h3 class="mt-2 text-gray-800 font-semibold">
                 <nuxt-link :to="`${postType}/${post.slug}`">
                    <span class="absolute inset-0"></span>
                    {{post.title}}
                </nuxt-link>
            </h3>
            <p class="mt-0.5 text-sm text-gray-500">Snowman</p>
            <p class=" text-sm  text-gray-600" v-if="post.createdAt">28k views - {{ formatDate(post.createdAt) }}</p>
    </div>
</div>
</template>

<script>
export default {
    name: 'Videos',
    props: {
        postType: {
            type: String,
            default: 'blog',
            validator: (val) => ['blog', 'projects', 'videos'].includes(val),
        },
        amount: {
            type: Number,
            default: 10,
            validator: (val) => val >= 0 && val < 100,
        },
        sortBy: {
            type: Object,
            default: () => ({
                key: 'slug',
                direction: 'desc' // you probably want 'asc' here
            }),
            validator: (obj) => typeof obj.key === 'string' && typeof obj.direction === 'string',
        }
    },
    data() {
        return {
            posts: [],
            loading: true,
        }
    },
    computed: {
        placeholderClasses() {
            const classes = ['w-full', 'w-2/3', 'w-5/6'];
            return [...Array.from({
                length: this.amount
            }, (v, i) => classes[i % classes.length])]; // repeats classes after one another
        }
    },
    async mounted() {
        this.loading = true;
        this.posts = await this.fetchPosts();
        this.loading = false;
    },
    methods: {
        formatDate(dateString) {
            const date = new Date(dateString)
            return date.toLocaleDateString(process.env.lang) || ''
        },
        async fetchPosts(
            postType = this.postType,
            amount = this.amount,
            sortBy = this.sortBy,
        ) {
            return this.$content(postType)
                .sortBy(sortBy.key, sortBy.direction)
                .limit(amount)
                .fetch()
                .catch((err) => console.error(err) || []);
        }
    },
}
</script>
