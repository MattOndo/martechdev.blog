<template>
  <div
    class="
      h-full
      overflow-hidden
      text-gray-700
      rounded-lg
      shadow-xl
      dark:bg-gray-800 dark:text-gray-300
      flex
      flex-col
    "
  >
    <g-link :to="`${post.node.path}/`" class="text-copy-primary">
      <g-image
        class="lg:h-48 md:h-36 w-full object-cover object-center"
        :src="
          post.node.thumbnail
            ? post.node.thumbnail.src
            : '/images/default-thumb.png'
        "
        :alt="post.node.title"
      />
    </g-link>
    <div class="p-8 m-0 flex flex-col h-full">
      <h2
        class="
          tracking-widest
          text-xs
          title-font
          font-medium
          mb-1
          text-primary-600
        "
      >
        {{ parentCategory(post.node.categories) }}
      </h2>
      <h3 class="title-font text-xl font-medium text-gray-900 mb-1">
        <g-link :to="`${post.node.path}/`" class="text-copy-primary">
          {{ post.node.title }}
        </g-link>
      </h3>
      <div
        class="
          inline-flex
          items-center
          leading-none
          text-sm
          mb-3
          justify-between
        "
      >
        <span>{{
          post.node.date
        }}</span>
        <span>
          <span class="mr-3">☕</span>
          <span>{{ post.node.timeToRead }} min read</span>
        </span>
      </div>
      <p class="leading-relaxed mb-3 flex flex-col grow" style="flex-grow: 1;">{{ post.node.summary }}</p>
      <div class="flex flex-col">
        <g-link
          :to="`${post.node.path}/`"
          class="text-primary-500 inline-flex items-center md:mb-2 lg:mb-0"
          >Read More
          <svg
            class="w-4 h-4 ml-2"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
            fill="none"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path d="M5 12h14"></path>
            <path d="M12 5l7 7-7 7"></path>
          </svg>
        </g-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['post'],
}
</script>
