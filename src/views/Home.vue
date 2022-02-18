<template>
  <div
    class="h-screen w-screen bg-[#fff] py-8 text-[#958277] font-[300] font-akaya flex relative z-20 transition-transform ease-in-out delay-500"
    :class="[show ? '-translate-y-full' : '']"
  >
    <div class="min-h-1/2 w-4/5 m-auto">
      <h1 class="font-honey text-3xl text-center tracking-[10px] mb-2">T&A</h1>
      <img src="../../public/decoration-2.png" class="w-full" />
      <h2
        class="uppercase text-center tracking-[1px] mt-6 text-[calc(20px*0.75)] animate-[fade-in-top_1s_ease-in-out_0.8s_both]"
      >
        Wedding of
      </h2>
      <h1
        class="text-center text-[calc(70px*0.75)] leading-[1] tracking-[2px] mt-4 pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_1.1s_both] font-honey"
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
        class="text-center font-akaya text-[calc(36px*0.75)] leading-[1] tracking-[2px] pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_2.1s_both]"
      >
        Ulvi Zasvia
      </h1>
      <p class="text-center animate-[fade-in-bottom_1s_ease-in-out_2.4s_both]">
        We invite you to attend our wedding
      </p>
      <div class="animate-[fade-in-top_1s_ease-in-out_2.5s_both]">
        <button
          @click="
            show = !show;
            modal = !modal;
          "
          class="animate-bounce px-2 py-2 bg-[#958277] text-white rounded-lg mt-8 hover:opacity-80 focus:outline-none active:outline-none text-base block mx-auto"
        >
          Open Invitation
        </button>
      </div>
      <img src="../../public/decoration-2.png" class="w-full mt-8 rotate-180" />
    </div>
  </div>

  <section
    class="w-screen h-screen bg-[#fff] absolute z-0 top-0 text-[#958277]"
    v-if="show"
    :class="[modal ? 'overflow-y-hidden' : 'overflow-y-visible']"
  >
    <Menu />
    <div class="min-h-screen w-screen flex bg-[#fff]">
      <Modal :withButton="false" @toggle-modal="modal = false" />

      <div class="min-h-1/2 w-4/5 m-auto">
        <img src="../../public/decoration-2.png" class="w-full rotate-180" />
        <h2 class="uppercase text-center text-2xl tracking-[1px] mt-8">
          وَمِنْ كُلِّ شَيْءٍ خَلَقْنَا زَوْجَيْنِ لَعَلَّكُمْ تَذَكَّرُونَ
        </h2>
        <p class="text-sm text-center mt-6">
          Artinya: “Dan segala sesuatu Kami Ciptakan Berpasang – pasangan supaya
          kamu mengingat kebesaran Allah.”(Adz-Dzariyat ayat 49)
        </p>
        <img src="../../public/decoration-2.png" class="w-full mt-8" />
      </div>
    </div>

    <div
      class="min-h-screen w-screen flex bg-[#fff] font-akaya"
      id="kata-pengantar"
    >
      <div class="min-h-1/2 w-4/5 m-auto pb-20">
        <img src="../../public/decoration-2.png" class="w-full mb-4" />
        <img
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
          src="../assets/images/bismillah.png"
          class="w-3/5 mx-auto mb-6"
          alt="bismillah"
        />
        <h1
          class="text-center text-3xl mb-8 font-honey"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Assalamualaikum Wr. Wb.
        </h1>
        <p
          class="text-base text-center mb-4 leading-5"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Tanpa mengurangi rasa hormat. Kami mengundang Bapak/Ibu/Saudara/i
          serta Kerabat sekalian untuk menghadiri acara pernikahan kami.
        </p>
        <p
          class="text-base text-center my-4 leading-5"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Dikarenakan Semakin berkembangnya penyebaran Covid-19 di Kota Jambi,
          merupakan suatu kehormatan dan kebahagiaan bagi kami apabila
          Bapak/Ibu/Saudara/i berkenan hadir pada saat resepsi dan memberikan
          Do’a Restu kepada kedua mempelai.
        </p>
        <img
          src="../../public/decoration-2.png"
          class="w-full mt-4 rotate-180"
        />
      </div>
    </div>

    <div
      class="min-h-screen w-screen flex bg-[#fff] font-akaya"
      id="mempelai-wanita"
    >
      <div class="min-h-1/2 w-full m-auto">
        <img src="../../public/decoration-2.png" class="w-full mb-4" />
        <h1
          class="text-center text-3xl mb-8 font-honey"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Mempelai Wanita
        </h1>

        <h2
          class="text-center text-4xl mb-8 font-honey"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <span class="text-2xl">Apt.</span> Tiara Aritsya,
          <span class="text-2xl">S.Farm.</span>
        </h2>
        <p
          class="text-center w-[90%] mx-auto"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <b>Putri</b> dari Bapak <b>Syaiful Anwar, S.H.</b> <br />& Ibu
          <b>Dra. Ermayani Arifin</b>
        </p>

        <img
          src="../../public/decoration-2.png"
          class="w-full mt-4 rotate-180"
        />
      </div>
    </div>

    <div
      class="min-h-screen w-screen flex bg-[#fff] font-akaya"
      id="mempelai-pria"
    >
      <div class="min-h-1/2 w-full m-auto">
        <img src="../../public/decoration-2.png" class="w-full mb-4" />
        <h1
          class="text-center text-3xl mb-8 font-honey"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Mempelai Pria
        </h1>

        <h2
          class="text-center text-4xl mb-8 font-honey"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Atar Satria Fikri, <span class="text-2xl">S.e., M.Ak.</span>
        </h2>
        <p
          class="text-center w-[90%] mx-auto"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <b>Putra</b> dari Bapak <b>Dr. H. M. Saman Sulaiman, M.A.</b> <br />
          & Ibu
          <b>Hj. Darniati</b>
        </p>

        <img
          src="../../public/decoration-2.png"
          class="w-full mt-4 rotate-180"
        />
      </div>
    </div>

    <div class="min-h-screen w-screen flex bg-[#fff] font-akaya pb-4" id="dday">
      <div class="min-h-1/2 w-4/5 m-auto">
        <img src="../../public/decoration-2.png" class="w-full mb-4" />
        <h1
          class="text-3xl text-center mb-8"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          إِن شَآءَ ٱللَّهُ
        </h1>

        <div
          class="flex justify-evenly items-center mb-8"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <div>
            <h1 class="text-4xl font-honey">Tiara</h1>
          </div>
          <div class="text-4xl font-honey">&</div>
          <div>
            <h1 class="text-4xl font-honey">Atar</h1>
          </div>
        </div>
        <p
          class="text-center mb-4"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          akan melaksanakan <b>Akad Nikah</b> dan <b>Resepsi</b> pada tanggal:
        </p>
        <h1
          class="text-xl text-center font-akaya mb-4"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Minggu, 6 Maret 2022
        </h1>
        <div
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <Countdown
            :time="dday"
            v-slot="{ days, hours, minutes, seconds }"
            v-if="dday > 0"
          >
            <div
              class="flex justify-center items-stretch text-white gap-4 text-akaya"
            >
              <div
                class="font-akaya rounded-lg bg-[#958277] w-[60px] p-1 text-center"
              >
                {{ days }} <br />Hari
              </div>
              <div
                class="font-akaya rounded-lg bg-[#958277] w-[60px] p-1 text-center"
              >
                {{ hours }} <br />Jam
              </div>
              <div
                class="font-akaya rounded-lg bg-[#958277] w-[60px] p-1 text-center"
              >
                {{ minutes }} <br />Menit
              </div>
              <div
                class="font-akaya rounded-lg bg-[#958277] w-[60px] p-1 text-center"
              >
                {{ seconds }} <br />Detik
              </div>
            </div>
          </Countdown>
        </div>
        <img
          src="../../public/decoration-2.png"
          class="w-full mt-6 rotate-180"
        />
      </div>
    </div>

    <div class="min-h-screen w-screen flex bg-[#fff] font-akaya" id="lokasi">
      <div class="min-h-1/2 w-4/5 m-auto">
        <img src="../../public/decoration-2.png" class="w-full mb-4" />
        <h1
          class="text-center text-3xl mb-4 font-honey"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Akad Nikah & Resepsi
        </h1>
        <img
          src="../assets/images/gedung.png"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
          class="w-3/5 mx-auto"
          alt=""
        />
        <h2
          class="text-center text-lg mt-4"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Gedung UIN Sulthan Thaha Saifuddin
        </h2>
        <h3
          class="text-center text-base mt-2"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Minggu, 6 <sup>th</sup> Maret 2022
        </h3>
        <p
          class="text-center text-xs mt-2"
          data-aos="zoom-in-up"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          Jl. Arif Rahman Hakim No.111, Simpang IV Sipin, Kec. Telanaipura, Kota
          Jambi, Jambi 36361
        </p>
        <div
          class="w-full flex"
          data-aos="zoom-in-down"
          data-aos-duration="1500"
          data-aos-once="true"
        >
          <a
            target="_blank"
            href="https://goo.gl/maps/2nPxsXJMoCHRqswDA"
            class="animate-bounce px-2 py-2 max-w-xl bg-[#958277] text-white rounded-lg mt-8 hover:opacity-80 focus:outline-none active:outline-none text-base text-center inline-block mx-auto"
          >
            Lihat Lokasi
          </a>
        </div>
        <img
          src="../../public/decoration-2.png"
          class="w-full mt-4 rotate-180"
        />
      </div>
    </div>
  </section>
</template>

<script>
import Modal from "../components/Modal.vue";
import Menu from "../components/Menu.vue";
import AOS from "aos";
import "aos/dist/aos.css";
import Countdown from "@chenfengyuan/vue-countdown";

export default {
  name: "Home",
  components: {
    Modal,
    Countdown,
    Menu,
  },
  data() {
    return {
      show: false,
      modal: false,
    };
  },
  computed: {
    dday() {
      return (
        new Date("March 6, 2022 09:00:00").getTime() - new Date().getTime()
      );
    },
  },
  created() {
    AOS.init();
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
