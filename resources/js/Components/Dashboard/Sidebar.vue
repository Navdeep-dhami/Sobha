<script setup>
import {Link } from '@inertiajs/vue3';
</script>
<template>
  <aside class="sidebar">
    <div class="logo">
      <h2>SOBHA <span class="constructions">CONSTRUCTIONS</span></h2>
    </div>

    <nav class="nav-menu">
      <div class="nav-item active">
        <span class="icon">
            <span class="material-symbols-outlined">home</span>
        </span>
        Dashboard
      </div>
      <div class="nav-item">
        <span class="icon">
            <span class="material-symbols-outlined">description</span>
        </span>
        Start New Configuration
      </div>
      <div class="nav-item">
        <span class="icon ">
            <span class="material-symbols-outlined">article</span>
        </span>
        View Existing Configurations
      </div>
      <div class="nav-item">
        <span class="icon">
            <span class="material-symbols-outlined">north_east</span>
        </span>
        Bulk Import
      </div>
      <div class="nav-item">
        <Link :href="route('report')">
        <span class="icon">
            <span class="material-symbols-outlined">article</span>
        </span>
        Reports
        </Link>
      </div>
    </nav>

    <div class="quick-actions">
      <h3>QUICK ACTIONS</h3>
      <div class="action-item">
        <span class="icon">
            <span class="material-symbols-outlined">add</span>
        </span>
        New Configuration
      </div>
      <div class="action-item">
        <span class="icon">
            <span class="material-symbols-outlined">north_east</span>
        </span>
        Bulk Import
      </div>
      <div class="action-item">
        <Link :href="route('report')">

        <span class="icon">
            <span class="material-symbols-outlined">article</span>
        </span>
        Reports
        </Link>
      </div>
    </div>
  </aside>
</template>

<style scoped>
.sidebar {
  width: 280px;
  background-color: #2c2c2c;
  color: white;
  padding: 20px;
  display: flex;
  flex-direction: column;
}

.logo {
  margin-bottom: 40px;
}

.logo h2 {
  font-size: 18px;
  font-weight: 700;
}

.constructions {
  font-size: 12px;
  font-weight: 400;
  opacity: 0.8;
}

.nav-menu {
  flex: 1;
}

.nav-item {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  margin-bottom: 4px;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.nav-item:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.nav-item.active {
  background-color: rgba(255, 255, 255, 0.15);
}

.nav-item .icon {
  margin-right: 12px;
  font-size: 16px;
}

.quick-actions {
  margin-top: 40px;
}

.quick-actions h3 {
  font-size: 12px;
  font-weight: 600;
  color: #888;
  margin-bottom: 16px;
  letter-spacing: 0.5px;
}

.action-item {
  display: flex;
  align-items: center;
  padding: 8px 16px;
  margin-bottom: 4px;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.2s;
  font-size: 14px;
}

.action-item:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.action-item .icon {
  margin-right: 12px;
  font-size: 14px;
}
</style>
