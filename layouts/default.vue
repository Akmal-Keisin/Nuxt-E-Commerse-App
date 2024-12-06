<template>
   <div class="flex h-screen bg-gray-900 text-gray-100">
      
      <!-- Sidebar -->
      <aside class="bg-gray-800 flex flex-col transform transition-transform duration-300 ease-in-out"
      :class="{ '-translate-x-full': !isSidebarOpen, 'w-64': isSidebarOpen }">
         <div class="px-6 py-4 text-lg font-semibold border-b border-gray-700">
            Simple E-Commerse
         </div>
         <nav class="flex-1 px-6 py-4 space-y-4">
            <a v-for="(item, index) in menuItems" :key="index" href="#"
               class="flex items-center space-x-4 px-4 py-2 rounded-md hover:bg-gray-700 transition">
               <span class="material-icons text-xl">{{ item.icon }}</span>
               <span>{{ item.label }}</span>
            </a>
         </nav>
      </aside>

      <!-- Main Content -->
      <main class="flex-1">
         <!-- Header -->
         <header class="bg-gray-800 text-gray-100 p-4 flex items-center space-x-4">
            <!-- Hamburger Button -->
            <button @click="toggleSidebar" class="p-2 rounded-md hover:bg-gray-700 transition">
               <span class="material-icons">menu</span>
            </button>
            <!-- Header Content -->
            <h1 class="text-xl font-bold">Dashboard</h1>
         </header>

         <!-- Content -->
         <div class="p-6">
            <h2 class="text-2xl font-semibold">Welcome to Nuxt 3</h2>
            <p class="mt-4 text-gray-300">This is the main content area.</p>
         </div>
      </main>
   </div>
</template>

<script setup>
const isSidebarOpen = ref(false);
const toggleSidebar = () => {
   isSidebarOpen.value = !isSidebarOpen.value;
}
const menuItems = [
   { icon: 'dashboard', label: 'Dashboard' },
   { icon: 'inventory_2', label: 'Products' },
   { icon: 'point_of_sale', label: 'Sales' },
   { icon: 'history', label: 'Sales Histories' },
];
</script>