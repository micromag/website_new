<template>
  <div class="bg-gray-900">
    <Header />
    <div class="relative isolate overflow-hidden pt-14">
      <img src="/public/cover.jpg" alt="micro:mag News, Reviews, Projects and Makes" class="absolute inset-0 -z-5 h-1/2 w-full object-cover" />

      <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
        
      </div>

      <!-- Tag Line -->
      <div class="text-center">
        <h1 class="text-4xl font-bold tracking-tight text-white sm:text-6xl">
          Micro:Bit, EdTech & Technology news
        </h1>
      </div>
      
      <!-- Blog -->
      <div class="relative px-4 pt-16 pb-20 sm:px-6 lg:pt-26 lg:pb-28 lg:px-10 bg-gray-900">
        <div class="relative mx-auto max-w-7xl bg-gray-900">
          <div class="text-center">
            <h1 class="text-3xl font-extrabold tracking-tight text-blue-400  md:text-7xl">
              Articles
            </h1>
          </div>
        
          <div class="grid max-w-lg gap-5 mx-auto mt-12 lg:grid-cols-3 lg:max-w-none">
            <ArticleCard
              v-for="article in articles"
              :key="article.content.title"
              :type="article.content.type"
              :title="article.content.title"
              :description="article.content.description"
              :slug="`/${article.slug}`"
              :author="article.content.author"
              :image="article.content.image.filename"
              :date="article.content.date.toLocaleDateString()"
            />
          </div>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<!--<script lang="ts">
  /*import Header from "~/components/Header.vue";
  import Footer from "~/components/Footer.vue";*/

  export default {
    async asyncData({ app }) {
            const res = await app.$storyapi.get('cdn/stories', {
                starts_with: 'articles/',
                resolve_relations: 'author',
            })

            // Let's convert content.date from a String to a Date
            const articles = res.data.stories.map((story: any) => {
                story.content.date = new Date(story.content.date)
                return story
            })

            return { articles } 
        },
    /*components: {
      Header,
      Footer,
    }*/
  };
</script>-->
