<script setup lang="ts">
import Header from "./partials/Header.vue"
import Sidebar from "./partials/Sidebar.vue"

</script>
<template>
  <div>
    <Header />   
    <div class="section">    
      <Sidebar />
      <div class="flex-1 flex flex-col overflow-hidden">
        <main class="flex-1 overflow-x-hidden overflow-y-auto">
          <div class="container mx-auto p-6">
            <slot />
          </div>
        </main>
        <!--PageFoot /-->
      </div>
    </div>
  </div>
</template>
