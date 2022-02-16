<template>
  <div class="font-source text-[#958277]">
    <button
      v-if="withButton"
      class="text-white rounded-lg shadow-lg bg-[#958277] px-3 py-2 hover:opacity-80 outline-none active:outline-none focus:outline-none"
      @click="toggleModal = !toggleModal"
    >
      Open Modal
    </button>

    <div
      v-if="toggleModal"
      class="fixed overflow-x-hidden overflow-y-hidden inset-0 flex justify-center items-center z-50"
    >
      <div class="relative mx-2 w-auto max-w-2xl">
        <div class="bg-white w-full rounded-lg shadow-2xl flex flex-col p-4">
          <div class="text-4xl mb-6 text-center font-honey">
            Protokol Kesehatan Covid-19
          </div>
          <span class="leading-5 text-center text-sm mb-6">
            Demi mendukung kesehatan bersama alangkah baiknya para tamu yang
            akan hadir memenuhi protokol kesehatan sebagai berikut:
          </span>
          <img src="../assets/images/prokes-covid.jpg" alt="" />
          <button
            class="rounded bg-[#958277] text-white px-3 py-2 m-auto mt-6"
            @click="toggleModal = false"
          >
            Baik, Saya Mengerti
          </button>
        </div>
      </div>
    </div>
    <div
      v-if="toggleModal"
      class="absolute z-40 inset-0 opacity-25 bg-black"
    ></div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["withButton"],
  data() {
    return {
      toggleModal: true,
    };
  },
};
</script>
