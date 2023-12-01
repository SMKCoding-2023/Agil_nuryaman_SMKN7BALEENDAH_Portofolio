<script setup>
const { data: posts } = await useAsyncData('latest-posts', () =>
  queryContent('/blog')
    .sort({ data: 1 })
    .limit(3)
    .find()
)
</script>

<template>
  <section>
    <h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Agil nuryaman</h1>
    <p class="text-base text-gray-900 p-2 italic">saya adalah ultraman orb</p>
  </section>

  <section class="flex flex-col md:flex-row">
    <div class="md:w-3/4">
      <h2 class="text-3xl font-bold mt-8">My Story</h2>
      <p class="text-lg py-2">
        I was born on January 1 2007 in Bandung, precisely in Baleendah sub-district in jelekong village.
      </p>
      <p class="text-lg py-2">
        I started my education at kindergarten in Alqonaah for 1 year and I continued my public elementary school at SDN jelekong for 6 years
      </p>
      <p class="text-lg py-2">
        and I continued my junior high school at Alqonaah for 3 years after junior high school I continued my education at SMK Negeri 7 Baleendah. During my time at SMKN I learned a lot about the world of IT.
      </p>
    </div>
    <img src="~/assets/images/me.png" class="w-1/2 md:max-w-sm p-8 mx-auto" />
  </section>
  <section>
    <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
    <div class="grid md:grid-cols-3 pt-8 gap-10">
      <Post :posts="posts" />
    </div>
  </section>
</template>

