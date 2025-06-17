<script setup>
import Sidebar from '@/components/Report/Sidebar.vue';
import Header from '@/components/Report/Header.vue';
import ConfigurationReports from '@/components/Report/Reports.vue';

</script>

<template>

  <div class="min-h-screen bg-gray-50">
    <div class="flex">
      <!-- Sidebar -->
      <Sidebar />

      <!-- Main Content -->
      <main class="flex-1 ml-64">
        <Header />
        <div class="p-6">
          <ConfigurationReports />
        </div>
      </main>
    </div>
  </div>
</template>
<!--
<Link :href="route('dashboard')">
                                    <ApplicationLogo
                                        class="block h-9 w-auto fill-current text-gray-800"
                                    />
                                </Link> -->
