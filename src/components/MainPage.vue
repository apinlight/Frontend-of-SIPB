<script setup lang="ts">
import AppTitle from './AppTitle.vue'
import NavSidebar from './NavSidebar.vue'
import DetailComponent from './DetailComponent.vue'
import ProfileLogout from './ProfileLogout.vue'
import CollapsiblePanel from './CollapsiblePanel.vue'
import PopupDialog from './PopupDialog.vue'
import { ref } from 'vue'

const showPopup = ref(true)
</script>

<template>
  <div class="flex h-screen">
    <!-- Sidebar -->
    <CollapsiblePanel class="w-64 bg-gray-100 border-r shadow-sm">
      <AppTitle />
      <NavSidebar />
    </CollapsiblePanel>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
      <!-- Header -->
      <div class="flex items-center justify-between bg-white px-6 py-4 shadow">
        <AppTitle />
        <ProfileLogout />
      </div>

      <!-- Content Area -->
      <DetailComponent class="flex-1 overflow-y-auto bg-gray-50 p-6">
        <!-- Slot untuk konten halaman -->
        <p class="text-gray-600">Selamat datang di Sistem Informasi Pencatatan Barang</p>
      </DetailComponent>
    </div>

    <!-- Popup (Contoh) -->
    <PopupDialog :show="showPopup" @close="showPopup = false">
      <div class="text-center">
        <h2 class="text-xl font-semibold mb-2">Popup Info</h2>
        <p class="text-gray-600">Ini adalah popup informasi.</p>
      </div>
    </PopupDialog>
  </div>
</template>
