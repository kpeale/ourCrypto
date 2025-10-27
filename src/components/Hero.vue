<script lang="ts">
export default {
  name: 'HeroSection',
  setup() {
    return {}
  },
}
</script>
<template>
  <section class="mt-32 flex items-center justify-center flex-col gap-12 relative">
    <div class="flex flex-col items-center justify-center">
      <h1
        class="font-bold font-yukita text-[40px] leading-[125%] max-w-[300px] nwsm:max-w-[327px] lg:max-w-[533px] mx-auto text-center"
      >
        <span class="text-[#2752E7]"> One platform </span> <br />
        <span class="text-[#2C3131]">all things Crypto</span>
      </h1>

      <div
        class="mt-3 lg:mt-4 max-w-[300px] nwsm:max-w-[327px] lg:max-w-[604px] flex items-center justify-center mx-auto"
      >
        <p class="text-[#626262] text-center font-regular text-[20px] lg:leading-[140%] font-inter">
          Open a free account in minutes right from your phone and make your money go further
        </p>
      </div>

      <div class="flex flex-col lg:flex-row mt-8 gap-3 items-center justify-center">
        <input
          type="text"
          class="border border-[#CACACA] rounded-[10px] w-[300px] nwsm:w-[327px] lg:w-[384px] px-6 lg:px-9 py-[18px] text-[#A9A9A9] text-[16px] font-inter leading-[150%] font-regular"
          placeholder="Email Address...."
        />

        <button
          class="bg-[#2752E7] px-10 py-[18px] rounded-[10px] text-white font-semibold text-[16px] lg:leading-[150%] w-[300px] nwsm:w-[327px] lg:w-[169px]"
        >
          Get started
        </button>
      </div>
    </div>

    <div class="hidden lg:flex mt-8">
      <img
        src="/safari.png"
        class="lg:w-[800px] xl:w-[979.59px] lsm:w-[1200px] jsm:w-[1400px] h-[600px] rounded-[7.65px] z-10"
      />
    </div>
  </section>
</template>
