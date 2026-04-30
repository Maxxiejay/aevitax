<script setup lang="ts">
import { Coins } from 'lucide-vue-next'
import Footer from './components/Footer.vue'
import Navbar from './components/Navbar.vue'
import Input from './components/ui/Input.vue'
import Slider from './components/ui/Slider.vue';
</script>

<template>
  <main class="">
    <Navbar />
    <section class="flex mx-12 border-x border-neutral-content py-14 px-12">
      <div class="">
        <h1 class="text-5xl font-bold text-primary">
          Calculate your <br />
          Personal <span class="italic font-light mr-2">PAYE</span> Tax
        </h1>

        <div
          class="flex items-center rounded-full font-medium w-fit border border-neutral-content mt-8 font-geist"
        >
          <div class="flex-1 bg-neutral rounded-full px-4 py-1 cursor-pointer">Annual Entry</div>
          <div class="flex-1 rounded-full text-nowrap px-4 py-1 cursor-pointer">Monthly Entry</div>
        </div>
        <div class="flex flex-col mt-8">
          <Input label="Name" />
          <Input label="Income (Annually)" leading="&#8358;" />
        </div>
        <div class="mt-8">
          <span class="flex gap-2 rounded-xl bg-neutral border border-neutral-content w-fit px-4 py-2 font-geist font-medium"><Coins /> Deductions (Optional)</span>
          <div class="flex items-center gap-8 mt-4">
            <Input label="NHF Contribution (Annualy)" placeholder="0" leading="&#8358;" />
            <Input label="House Rent (Annually)" placeholder="0" leading="&#8358;" />
          </div>
          <div class="flex items-center gap-8 mt-4">
            <Input label="Life Insurance Premium (You & Spouse)" placeholder="0" leading="&#8358;" />
            <Input label="NHIS Contribution (Annually)" placeholder="0" leading="&#8358;" />
          </div>
          <div class="flex items-center gap-8 mt-4 font-geist">
            <div class="flex flex-col w-full gap-8">
              <span class="text-accent font-medium">Owner-Occupied Home Loan Interest</span>
              <Slider :v-model="10" />
            </div>
            <div class="flex flex-col w-full gap-8">
              <span class="text-accent font-medium">Pension Contribution (Annually)</span>
              <Slider :v-model="10" />
            </div>
          </div>
        </div>
      </div>
    </section>
    <Footer />
  </main>
</template>

<style scoped></style>
