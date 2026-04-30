<template>
    <nav class="flex items-center justify-between px-12 py-4 bg-neutral w-full border-b border-neutral-content">
        <div class="flex items-center gap-10">
            <img :src="logoLight" alt="Aevitax Logo" class="w-24">
            <div class="flex gap-6">
                <span class="text-accent font-semibold cursor-pointer">Personal Tax</span>
                <span class="text-neutral-content font-semibold cursor-pointer">Company Tax</span>
            </div>
        </div>
        <div class="flex items-center gap-2 bg-white border border-neutral-content rounded-lg">
           <span class="bg-neutral-content border-r border-neutral-content p-2 rounded-lg cursor-pointer">
                <Sun :size="16" />
           </span>
           <span class="p-2 cursor-pointer">
                <CircleQuestionMark :size="16" />
           </span>
           <span class="p-2 cursor-pointer">
                <Bell :size="16" />
           </span>
        </div>
    </nav>
</template>

<script setup lang="ts">
import logoDark from '@/assets/images/logo-dark.svg';
import logoLight from '@/assets/images/logo-light.svg';
import { Bell, CircleQuestionMark, Sun } from 'lucide-vue-next';
</script>

<style scoped>

</style>