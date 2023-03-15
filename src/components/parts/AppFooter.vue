<template>
  <footer class="bg-background-tertiary body-font">
    <div class="container p-8 pt-20 flex flex-col md:flex-row justify-between mx-auto items-end">
      <div class="w-full md:w-80 md:order-1 mb-4 md:mb-0">
        <a
          class="
            flex
            title-font
            font-medium
            items-center
            md:justify-start
            justify-center
            text-gray-900
          "
        >
          <span class="site-logo"><site-logo /></span>
        </a>
        <p class="mt-2 text-sm text-center sm:text-left">
          {{ $static.metadata.siteDescription }}
        </p>
      </div>
      <div
        class="w-full md:w-1/2 md:order-0"
      >
        <p class="text-xs text-center sm:text-left">
          {{ `© ${new Date().getFullYear()} ${$static.metadata.siteName}` }} —
          <a
            :href="$static.metadata.siteAuthorUrl"
            rel="noopener noreferrer"
            class="text-gray-500 ml-1"
            target="_blank"
            >{{ `@${$static.metadata.siteAuthor}` }}</a
          >
          | <g-link class="text-gray-500 font-light" to="/privacy-policy/">Privacy Policy</g-link>
        </p>
      </div>
    </div>
  </footer>
</template>

<static-query>
query {
  metadata {
    siteName
    siteDescription
    siteAuthor
    siteAuthorUrl
  }
}
</static-query>

<script>
export default {
  components: {
    SiteLogo: () => import('~/components/SiteLogo.vue'),
  },
}
</script>
