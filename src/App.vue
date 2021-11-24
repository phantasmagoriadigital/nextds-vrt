<template>
  <div class="min-h-full">
    <nav class="bg-pink-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-16">
          <div class="flex items-center">
            <div class="flex-shrink-0"></div>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <router-link
                  to="/"
                  class="link px-3 py-2 rounded-md text-sm font-medium"
                  >Dashboard</router-link
                >
                <router-link
                  to="/settings"
                  class="link px-3 py-2 rounded-md text-sm font-medium"
                  >Settings</router-link
                >
              </div>
            </div>
          </div>

          <div class="-mr-2 flex md:hidden">
            <button
              @click.prevent="open = !open"
              type="button"
              class="
                bg-pink-800
                inline-flex
                items-center
                justify-center
                p-2
                rounded-md
                text-pink-400
                hover:text-white hover:bg-pink-700
                focus:outline-none
                focus:ring-2
                focus:ring-offset-2
                focus:ring-offset-pink-800
                focus:ring-white
              "
              aria-controls="mobile-menu"
              aria-expanded="false"
            >
              <span class="sr-only">Open main menu</span>

              <MenuIcon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
              <XIcon v-else class="block h-6 w-6" aria-hidden="true" />
            </button>
          </div>
        </div>
      </div>

      <div class="md:hidden" id="mobile-menu">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <!-- Current: "bg-pink-900 text-white", Default: "text-pink-300 hover:bg-pink-700 hover:text-white" -->
          <router-link
            to="/"
            class="
              link
              bg-pink-900
              text-white
              block
              px-3
              py-2
              rounded-md
              text-base
              font-medium
            "
            >Dashboard</router-link
          >

          <router-link
            to="/settings"
            class="
              link
              text-pink-300
              hover:bg-pink-700 hover:text-white
              block
              px-3
              py-2
              rounded-md
              text-base
              font-medium
            "
            >Settings</router-link
          >
        </div>
      </div>
    </nav>

    <header class="bg-white shadow">
      <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
        <h1 class="text-3xl font-bold text-pink-900">
          NextDS Design System Toolchain
        </h1>
      </div>
    </header>
    <main>
      <div class="max-w-7xl mx-auto py-6 sm:px-6 lg:px-8">
        <router-view></router-view>
      </div>
    </main>
    <footer class="bg-pink-800 absolute inset-x-0 bottom-0 h-16">
      <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
        <h1 class="text-pink-400">
        NextDS
        </h1>
      </div>
      </footer>
  </div>
</template>

<script>
import { MenuIcon, XIcon } from "@heroicons/vue/solid";

export default {
  components: {
    MenuIcon,
    XIcon,
  },
  data() {
    return {
      open: false,
    };
  },
};
</script>

<style scoped>
.link:not(.router-link-active) {
  @apply text-pink-300 hover:bg-pink-700 hover:text-white;
}
.link.router-link-active {
  @apply bg-pink-900 text-white;
}
</style>
