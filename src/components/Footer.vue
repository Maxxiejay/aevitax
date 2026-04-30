<template>
    <footer class="flex items-center justify-between px-12 py-4 bg-neutral w-full font-geist border-t border-neutral-content">
        <div class="flex items-center gap-4">
            <span>Designed by Mayowa<img :src="Mayowa" alt="Mayowa" class="w-6 h-6 rounded-full inline ml-2">,</span>
            <span>Built by Maxwell<img :src="Maxwell" alt="Maxwell" class="w-6 h-6 rounded-full inline ml-2">.</span>
        </div>
        <div>Tax Calculator based on the Nigeria 2026 Tax laws</div>
        <div>
           All rights reserved &copy; 2026
        </div>
    </footer>
</template>

<script setup lang="ts">
import Mayowa from '@/assets/images/mayowa.png';
import Maxwell from '@/assets/images/amazingmax.png';
</script>

<style scoped>

</style>