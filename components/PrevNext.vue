<template>
  <div v-if="prev || next" class="flex justify-between">
    <NuxtLink
      v-if="prev"
      :to="{ name: 'articles-slug', params: { slug: prev.slug } }"
      :class="linkStyles"
    >
      {{ prev.title }}
    </NuxtLink>
    <span v-else>&nbsp;</span>
    <NuxtLink
      v-if="next"
      :to="{ name: 'articles-slug', params: { slug: next.slug } }"
      :class="linkStyles"
    >
      {{ next.title }}
    </NuxtLink>
    <span v-else>&nbsp;</span>
  </div>
</template>

<script>
export default {
  name: 'PrevNext',
  props: {
    prev: {
      type: Object,
      default: null,
    },
    next: {
      type: Object,
      default: null,
    },
  },
  computed: {
    linkStyles() {
      return 'bg-indigo-400 text-white px-4 py-1 hover:bg-indigo-500 transform duration-500 ease-in-out';
    },
  },
};
</script>
