<template>
  <div class="flex h-screen bg-gray-100">
    <!-- Sidebar -->
    <aside class="w-64 bg-white shadow-md hidden md:block flex-shrink-0">
      <div class="p-4 border-b">
        <h1 class="text-xl font-semibold text-gray-800">Business App</h1>
      </div>
      <nav class="mt-4">
        <a href="#" class="block px-4 py-2 text-gray-700 hover:bg-blue-100 hover:text-blue-600 rounded-md mx-2">Dashboard</a>
        <a href="#" class="block px-4 py-2 mt-1 text-gray-700 hover:bg-blue-100 hover:text-blue-600 rounded-md mx-2">Reports</a>
        <a href="#" class="block px-4 py-2 mt-1 text-gray-700 hover:bg-blue-100 hover:text-blue-600 rounded-md mx-2">Settings</a>
        <!-- Add more navigation items here -->
      </nav>
    </aside>

    <!-- Main Content Area -->
    <div class="flex-1 flex flex-col overflow-hidden">
      <!-- Header -->
      <header class="bg-white shadow-sm border-b">
        <div class="flex items-center justify-between px-6 py-3">
          <div>
            <button class="text-gray-500 focus:outline-none md:hidden">
              <!-- Mobile Menu Icon -->
              <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
            <span class="text-lg font-medium text-gray-700 ml-2">Page Title</span>
          </div>
          <div>
            <!-- Header actions (e.g., User profile) -->
            <button class="text-gray-600">User Profile</button>
          </div>
        </div>
      </header>

      <!-- Content -->
      <main class="flex-1 overflow-x-hidden overflow-y-auto bg-gray-100 p-6">
        <!-- Router view to display page content -->
        <router-view />
      </main>
    </div>
  </div>
</template>

<script setup lang="ts">
// Imports and logic remain largely the same, focusing on layout structure here.
const route = useRoute()

useHead({
  title: () => route.meta.title || 'Modern Business App',
  meta: [
    {
      property: 'og:title',
      content: () => route.meta.title || 'Modern Business App',
    },
    {
      name: 'twitter:title',
      content: () => route.meta.title || 'Modern Business App',
    },
  ],
})
</script>

<style scoped>
/* Add any component-specific styles if needed, though Tailwind is preferred */
</style>

