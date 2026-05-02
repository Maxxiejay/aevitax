<script setup lang="ts">
import { Coins } from 'lucide-vue-next'
import Footer from './components/Footer.vue'
import Navbar from './components/Navbar.vue'
import Input from './components/ui/Input.vue'
import Slider from './components/ui/Slider.vue'
</script>

<template>
  <main class="">
    <Navbar />
    <section class="flex gap-16 mx-12 border-x border-neutral-content py-14 px-12">
      <div class="flex-1">
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
          <span
            class="flex gap-2 rounded-xl bg-neutral border border-neutral-content w-fit px-4 py-2 font-geist font-medium"
            ><Coins /> Deductions (Optional)</span
          >
          <div class="flex items-center gap-8 mt-4">
            <Input label="NHF Contribution (Annualy)" placeholder="0" leading="&#8358;" />
            <Input label="House Rent (Annually)" placeholder="0" leading="&#8358;" />
          </div>
          <div class="flex items-center gap-8 mt-4">
            <Input
              label="Life Insurance Premium (You & Spouse)"
              placeholder="0"
              leading="&#8358;"
            />
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
      <div class="flex-1 flex flex-col gap-8">
        <div class="flex flex-col gap-8 p-6 border border-neutral-content rounded-2xl">
          <div class="flex justify-between">
            <div class="flex flex-col gap-6">
              <span class="text-accent font-geist font-medium">Results for</span>
              <span class="text-primary font-medium text-4xl">Mayowa</span>
              <div
                class="flex items-center rounded-full font-medium w-fit border border-neutral-content font-geist"
              >
                <div class="flex-1 bg-neutral rounded-full px-4 py-1 cursor-pointer">
                  Annual Results
                </div>
                <div class="flex-1 rounded-full text-nowrap px-4 py-1 cursor-pointer">
                  Monthly Results
                </div>
              </div>
            </div>
            <span class="h-38 w-38 rounded-2xl bg-neutral"></span>
          </div>
          <div class="flex w-full">
            <div class="flex-1 flex flex-col gap-2 border-r border-neutral-content pr-6">
              <span class="text-accent font-geist font-medium">PAYE Tax due</span>
              <span class="text-primary font-bold text-4xl">&#8358;176,250.00</span>
              <div class="flex justify-between text-sm">
                <span class="text-accent font-geist font-medium">Monthly Tax size</span>
                <span class="text-primary font-bold">&#8358;20,000.00</span>
              </div>
            </div>
            <div class="flex-1 flex flex-col gap-2 pl-6">
              <span class="text-accent font-geist font-medium">Take Home Pay</span>
              <span class="text-primary font-bold text-4xl">&#8358;125,250.00</span>
              <div class="flex justify-between text-sm">
                <span class="text-accent font-geist font-medium">Monthly Take Home</span>
                <span class="text-primary font-bold">&#8358;20,000.00</span>
              </div>
            </div>
          </div>
        </div>
        <div class="flex flex-col gap-8 p-6 border border-neutral-content rounded-2xl">
          <div
            class="flex items-center rounded-full font-medium w-fit border border-neutral-content font-geist"
          >
            <div class="flex-1 bg-neutral rounded-full px-4 py-1 cursor-pointer text-nowrap">Income Breakdown</div>
            <div class="flex-1 rounded-full text-nowrap px-4 py-1 cursor-pointer">
              Tax Brackets
            </div>
          </div>
          <div class="flex flex-col">
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
            <div class="flex justify-between py-4 border-b border-neutral-content">
              <span class="text-gray-600 font-geist">Gross Annual Income</span>
              <span class="text-primary font-bold">&#8358;1,200,000.00</span>
            </div>
          </div>
          <div class="flex justify-between">
            <span class="text-primary font-medium font-geist text-2xl">Taxable Income</span>
            <span class="text-primary font-bold text-2xl">&#8358;1,200,000.00</span>
          </div>
        </div>
        <button class="bg-secondary text-primary rounded-full px-4 py-2 font-geist font-bold">Download Report</button>
      </div>
    </section>
    <Footer />
  </main>
</template>

<style scoped></style>
