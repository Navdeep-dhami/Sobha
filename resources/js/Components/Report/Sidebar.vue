<script setup>
import {Link } from '@inertiajs/vue3';
</script>
<template>
  <aside class="fixed left-0 top-0 w-64 h-full bg-white border-r border-gray-200 z-10">
    <div class="p-6">
      <div class="flex items-center space-x-3">
        <div class="w-8 h-8 bg-sobha-gold rounded flex items-center justify-center">
          <div class="w-6 h-6 bg-sobha-gold rounded-sm flex flex-col justify-center">
            <div class="h-1 bg-white mx-1 mb-0.5"></div>
            <div class="h-1 bg-white mx-1 mb-0.5"></div>
            <div class="h-1 bg-white mx-1"></div>
          </div>
        </div>
        <div>
          <h1 class="text-xl font-bold text-gray-900">SOBHA</h1>
          <p class="text-xs text-gray-500 uppercase tracking-wide">CONSTRUCTIONS</p>
        </div>
      </div>
    </div>

    <nav class="mt-8">
      <ul class="space-y-2 px-4">
        <li>

        <Link :href="route('dashboard')" class="flex items-center space-x-3 px-4 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
              <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
            </svg>
            <span>Dashboard</span>
        </Link>
        </li>
        <li>
          <a href="#" class="flex items-center space-x-3 px-4 py-2 bg-gray-100 text-gray-900 rounded-lg">
            <div class="w-6 h-6 bg-gray-700 rounded text-white text-xs flex items-center justify-center font-medium">5</div>
            <span class="font-medium">Reports</span>
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center space-x-3 px-4 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
              <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
            </svg>
            <span>Bulk Import</span>
          </a>
        </li>
      </ul>
    </nav>

    <div class="absolute bottom-0 left-0 right-0 p-4 border-t border-gray-200">
      <h3 class="text-sm font-medium text-gray-500 uppercase tracking-wide mb-4">Help & Support</h3>
      <a href="#" class="flex items-center space-x-3 px-4 py-2 text-gray-600 hover:bg-gray-50 rounded-lg">
        <div class="w-6 h-6 bg-gray-400 rounded-full text-white text-xs flex items-center justify-center">?</div>
        <span>Help</span>
      </a>
    </div>
  </aside>
</template>
