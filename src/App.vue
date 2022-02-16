<template>
  <div
    class="h-screen w-screen bg-[#fff] py-8 text-[#958277] font-[300] font-source flex relative z-20 transition-transform ease-in-out delay-500"
    :class="[show ? '-translate-y-full' : '']"
  >
    <div class="min-h-1/2 w-4/5 m-auto">
      <h1 class="font-festive text-5xl text-center tracking-[10px] -mb-2">
        T&A
      </h1>
      <img src="../public/decoration-2.png" class="w-full" />
      <h2
        class="uppercase text-center tracking-[1px] mt-8 text-[calc(20px*0.75)] animate-[fade-in-top_1s_ease-in-out_0.8s_both]"
      >
        Wedding of
      </h2>
      <h1
        class="text-center text-[calc(60px*0.75)] leading-[1] tracking-[2px] pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_1.1s_both] font-bold"
      >
        Tiara & Atar
      </h1>
      <h2
        class="uppercase text-center tracking-[1px] my-2 text-[calc(20px*0.75)] animate-[fade-in-bottom_1s_ease-in-out_1.5s_both]"
      >
        Sunday, March 6<sup class="lowercase">th</sup> 2022
      </h2>

      <h2
        class="uppercase text-center tracking-[1px] mt-12 text-[calc(16px*0.75)] animate-[fade-in-top_1s_ease-in-out_1.8s_both]"
      >
        Dear
      </h2>
      <h1
        class="text-center text-[calc(36px*0.75)] leading-[1] tracking-[2px] pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_2.1s_both] font-bold"
      >
        Ulvi Zasvia
      </h1>
      <p class="text-center animate-[fade-in-bottom_1s_ease-in-out_2.4s_both]">
        We invite you to attend our wedding
      </p>
      <div class="animate-[fade-in-top_1s_ease-in-out_2.5s_both]">
        <button
          @click="show = !show"
          class="animate-bounce px-2 py-2 bg-[#958277] text-white rounded-lg mt-8 hover:opacity-80 text-base block mx-auto"
        >
          Open Invitation
        </button>
      </div>
      <img src="../public/decoration-2.png" class="w-full mt-8 rotate-180" />
    </div>
  </div>

  <section
    class="w-screen h-screen bg-[#fff] absolute z-0 top-0 flex text-[#958277]"
    v-if="show"
  >
    <Modal :withButton="false" />

    <div class="min-h-1/2 w-4/5 m-auto">
      <img src="../public/decoration-2.png" class="w-full rotate-180" />
      <h2 class="uppercase text-center text-2xl tracking-[1px] mt-8">
        وَمِنْ كُلِّ شَيْءٍ خَلَقْنَا زَوْجَيْنِ لَعَلَّكُمْ تَذَكَّرُونَ
      </h2>
      <p class="text-sm text-center mt-6">
        Artinya: “Dan segala sesuatu Kami Ciptakan Berpasang – pasangan supaya
        kamu mengingat kebesaran Allah.”(Adz-Dzariyat ayat 49)
      </p>
      <img src="../public/decoration-2.png" class="w-full mt-8" />
    </div>
  </section>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style>
@-webkit-keyframes fade-in-top {
  0% {
    -webkit-transform: translateY(-50px);
    transform: translateY(-50px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@keyframes fade-in-top {
  0% {
    -webkit-transform: translateY(-50px);
    transform: translateY(-50px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@-webkit-keyframes scale-in-bottom {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
    -webkit-transform-origin: 50% 100%;
    transform-origin: 50% 100%;
    opacity: 1;
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
    -webkit-transform-origin: 50% 100%;
    transform-origin: 50% 100%;
    opacity: 1;
  }
}
@keyframes scale-in-bottom {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
    -webkit-transform-origin: 50% 100%;
    transform-origin: 50% 100%;
    opacity: 1;
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
    -webkit-transform-origin: 50% 100%;
    transform-origin: 50% 100%;
    opacity: 1;
  }
}
@-webkit-keyframes fade-in-bottom {
  0% {
    -webkit-transform: translateY(50px);
    transform: translateY(50px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
@keyframes fade-in-bottom {
  0% {
    -webkit-transform: translateY(50px);
    transform: translateY(50px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}
</style>
