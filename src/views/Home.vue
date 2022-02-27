<template>
  <div class="h-screen w-screen flex justify-center">
    <Loading v-if="loading" />
    <div
      class="h-full w-full md:w-1/3 md:mx-auto bg-[#fff] py-8 text-[#958277] font-[300] font-akaya flex relative z-20 transition-transform ease-in-out delay-500"
      :class="[show ? '-translate-y-full' : '']"
    >
      <audio id="audio" loop>
        <source src="../assets/audios/backsound.mp3" type="audio/mpeg" />
      </audio>
      <div class="min-h-1/2 w-4/5 m-auto">
        <h1 class="font-honey text-3xl text-center tracking-[10px] mb-2">
          T&A
        </h1>
        <img src="../../public/decoration-2.png" class="w-full" />
        <h2
          class="uppercase text-center tracking-[1px] mt-6 text-[calc(20px*0.75)] animate-[fade-in-top_1s_ease-in-out_0.8s_both]"
        >
          Pernikahan dari
        </h2>
        <h1
          class="text-center text-[calc(70px*0.75)] leading-[1] tracking-[2px] mt-4 pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_1.1s_both] font-honey"
        >
          Tiara & Atar
        </h1>
        <h2
          class="uppercase text-center tracking-[1px] my-2 text-[calc(20px*0.75)] animate-[fade-in-bottom_1s_ease-in-out_1.5s_both]"
        >
          Minggu, 6 Maret 2022
        </h2>

        <h2
          class="uppercase text-center tracking-[1px] mt-12 text-[calc(14px*0.75)] animate-[fade-in-top_1s_ease-in-out_1.8s_both]"
        >
          Yang terhormat
        </h2>
        <h1
          class="text-center font-akaya text-[calc(36px*0.75)] leading-[1] tracking-[2px] pt-4 pb-4 animate-[scale-in-bottom_1s_ease-in-out_2.1s_both] capitalize"
        >
          {{ undangan.replace(/\./g, " ").replace(/\=/g, "&") }}
        </h1>
        <p
          class="text-center animate-[fade-in-bottom_1s_ease-in-out_2.4s_both] px-4"
        >
          Kami Mengundang Anda Untuk Hadir Di Acara Pernikahan Kami
        </p>
        <div class="animate-[fade-in-top_1s_ease-in-out_2.5s_both]">
          <button
            @click="clickOpen"
            class="animate-bounce px-2 py-2 bg-[#958277] text-white rounded-lg mt-8 hover:opacity-80 focus:outline-none active:outline-none text-base block mx-auto"
          >
            <i class="fas fa-heart text-red-500 shadow"></i> Buka Undangan
          </button>
        </div>
        <img
          src="../../public/decoration-2.png"
          class="w-full mt-8 rotate-180"
        />
      </div>
    </div>

    <div
      class="w-full h-full md:w-1/3 md:mx-auto bg-[#fff] absolute z-0 top-0 text-[#958277]"
      v-if="show"
      :class="[modal ? 'overflow-y-hidden' : 'overflow-y-visible']"
    >
      <Menu :modal="modal" class="md:w-1/3" />

      <button
        @click="onClickMuted"
        class="z-[48] fixed bottom-[40%] right-1 outline-none active:border-none focus:border-none p-2 bg-[#958277] rounded-full flex"
      >
        <i
          class="text-white fas m-auto align-middle"
          :class="[!muted ? 'fa-volume-up' : 'fa-volume-mute']"
        ></i>
      </button>

      <Modal :withButton="false" @toggle-modal="modal = false" />
      <!-- <div class="min-h-screen w-screen flex bg-[#fff]">

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
    </div> -->

      <div
        class="min-h-screen w-full md:mx-auto flex bg-[#fff] font-akaya"
        id="kata-pengantar"
      >
        <div class="min-h-1/2 w-4/5 m-auto pb-36">
          <img src="../../public/decoration-2.png" class="w-full mb-4" />
          <img
            src="../assets/images/bismillah.png"
            class="w-3/5 mx-auto mb-6"
            alt="bismillah"
          />
          <h1 class="text-center text-3xl mb-8 font-honey">
            Assalamualaikum Wr. Wb.
          </h1>
          <p
            class="text-base text-center mb-4 leading-5"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Mahasuci Allah SWT telah menciptakan mahluk hidup dengan
            berpasang-pasangan. Begitu pula manusia. Sungguh besar rahmat dan
            karunia yang diberikan-Nya kepada keluarga kami.
          </p>
          <p
            class="text-base text-center my-4 leading-5"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Maka izinkan kami mengundang sekaligus mengharapkan doa restu dari
            bapak/ibu dan saudara/i dalam acara pernikahan kami
          </p>
          <img
            src="../../public/decoration-2.png"
            class="w-full mt-4 rotate-180"
          />
        </div>
      </div>

      <div
        class="min-h-screen w-full mx-auto flex bg-[#fff] font-akaya"
        id="mempelai-wanita"
      >
        <div class="min-h-1/2 w-full m-auto pb-36">
          <img src="../../public/decoration-2.png" class="w-full mb-4" />
          <h1
            class="text-center text-3xl mb-4 font-honey"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Mempelai Wanita
          </h1>

          <div class="columns-2 flex">
            <div class="w-1/3 h-full relative">
              <img
                src="../assets/images/tiara.png"
                class="w-full h-full"
                data-aos="zoom-in-up"
                data-aos-duration="1500"
                data-aos-once="true"
                alt=""
              />
            </div>

            <div class="m-auto w-2/3">
              <h2
                class="text-center text-3xl px-2 font-hurricane w-full"
                data-aos="zoom-in-up"
                data-aos-duration="1500"
                data-aos-once="true"
              >
                <span class="text-xl">apt.</span> Tiara Aristya,
                <span class="text-xl">S.Farm.</span>
              </h2>
              <p
                class="text-center w-full text-sm mx-auto mt-4 leading-4 px-2"
                data-aos="zoom-in-down"
                data-aos-duration="1500"
                data-aos-once="true"
              >
                <b>Putri</b> dari Bapak <br />
                <b>Syaiful Anwar, S.H.</b> <br />
                & Ibu <b>Dra. Ermayani</b>
              </p>
            </div>
          </div>

          <img
            src="../../public/decoration-2.png"
            class="w-full mt-4 rotate-180"
          />
        </div>
      </div>

      <div
        class="min-h-screen w-full flex bg-[#fff] font-akaya"
        id="mempelai-pria"
      >
        <div class="min-h-1/2 w-full m-auto pb-36">
          <img src="../../public/decoration-2.png" class="w-full mb-4" />
          <h1
            class="text-center text-3xl mb-4 font-honey"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Mempelai Pria
          </h1>

          <div class="columns-2 flex">
            <div class="m-auto w-2/3">
              <h2
                class="text-center text-2xl px-2 font-hurricane"
                data-aos="zoom-in-up"
                data-aos-duration="1500"
                data-aos-once="true"
              >
                Atar Satria Fikri, <span class="text-xl">S.E., M.Ak.</span>
              </h2>

              <p
                class="text-center w-[90%] text-sm mx-auto leading-4 mt-4 px-2"
                data-aos="zoom-in-down"
                data-aos-duration="1500"
                data-aos-once="true"
              >
                <b>Putra</b> dari Bapak
                <b> <br />Dr. H. M. Saman Sulaiman, M.A.</b>
                <br />
                & Ibu
                <b>Hj. Darniati</b>
              </p>
            </div>

            <div class="w-1/3 h-full relative">
              <img
                src="../assets/images/atar.png"
                class="w-full h-full"
                data-aos="zoom-in-up"
                data-aos-duration="1500"
                data-aos-once="true"
                alt=""
              />
            </div>
          </div>

          <img
            src="../../public/decoration-2.png"
            class="w-full mt-4 rotate-180"
          />
        </div>
      </div>

      <div class="min-h-screen w-full flex bg-[#fff] font-akaya" id="dday">
        <div class="min-h-1/2 w-full m-auto pb-36">
          <img src="../../public/decoration-2.png" class="w-full mb-4" />

          <div class="w-full h-full relative">
            <!-- <img
            src="../assets/images/ta-2.png"
            class="w-full h-full"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
            alt=""
          /> -->
          </div>

          <div class="w-full h-full py-4">
            <div
              class="flex justify-evenly items-center mb-4"
              data-aos="zoom-in-down"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              <h1 class="text-4xl font-honey mt-2">Tiara & Atar</h1>
            </div>
            <p
              class="text-center mb-4 px-4"
              data-aos="zoom-in-up"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              akan melaksanakan
            </p>
            <div
              class="w-[80%] bg-[url(./ta-1.jpg)] bg-[#cfc3bd] h-[170px] bg-blend-multiply bg-center bg-cover text-white p-4 mx-auto rounded-xl border-[1px] border-[#CED4D9] mb-4 flex flex-col justify-end shadow-slate-400 shadow-lg"
              data-aos="zoom-in-down"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              <h1 class="font-honey text-xl text-center mb-4">Akad Nikah</h1>
              <p class="text-center text-sm">
                <i class="fas fa-calendar"></i> Minggu, 6 Maret 2022
              </p>
              <p class="text-center text-sm">
                <i class="fas fa-clock"></i> 08:00 - 10:00 WIB
              </p>
            </div>
            <div
              class="w-[80%] bg-[url(./ta-2.jpeg)] bg-[#dfd1c4] h-[170px] bg-blend-multiply bg-center bg-cover text-white p-4 mx-auto rounded-xl border-[1px] border-[#CED4D9] mb-4 flex flex-col justify-end shadow-slate-400 shadow-lg"
              data-aos="zoom-in-down"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              <h1 class="font-honey text-xl text-center mb-4">Resepsi</h1>
              <p class="text-center text-sm">
                <i class="fas fa-calendar"></i> Minggu, 6 Maret 2022
              </p>
              <p class="text-center text-sm">
                <i class="fas fa-clock"></i> 11:00 - Selesai WIB
              </p>
            </div>

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
          </div>

          <!-- <img
          src="../../public/decoration-2.png"
          class="w-full mt-6 rotate-180"
        /> -->
        </div>
      </div>

      <div class="min-h-screen w-full flex bg-[#fff] font-akaya" id="lokasi">
        <div class="min-h-1/2 w-4/5 m-auto pb-36">
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
            Jl. Arif Rahman Hakim No.111, Simpang IV Sipin, Kec. Telanaipura,
            Kota Jambi, Jambi 36361
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

      <div class="min-h-screen w-full flex bg-[#fff] font-akaya" id="ucapan">
        <div class="min-h-1/2 px-6 m-auto pb-36">
          <img src="../../public/decoration-2.png" class="w-full mb-4" />
          <h1
            class="text-center text-3xl mb-4 font-honey"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Ucapkan Sesuatu
          </h1>

          <p
            class="text-center mb-4"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            Berikan Ucapan & Do'a Restu
          </p>

          <input
            type="text"
            class="p-2 border-2 border-[#CED4D9] rounded-lg w-full mb-4 bg-[#FFF9F6] text-[#958277] placeholder:text-[#958277] font-sans text-[12px]"
            placeholder="Nama Anda"
            v-model="nama"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
          />

          <select
            class="w-full rounded-lg p-2 border-2 border-[#CED4D9] mb-4 bg-[#FFF9F6] text-[#958277] placeholder:text-[#958277] font-sans text-[12px]"
            v-model="konfirmasi"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            <option :value="null">Pilih Konfirmasi Kehadiran</option>
            <option value="hadir">Hadir</option>
            <option value="tidak">Tidak Hadir</option>
          </select>

          <textarea
            class="p-2 border-2 border-[#CED4D9] rounded-lg w-full mb-4 bg-[#FFF9F6] text-[#958277] placeholder:text-[#958277] font-sans text-[12px]"
            v-model="ucap"
            cols="30"
            rows="3"
            placeholder="Berikan Ucapan & Do'a Restu"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
          ></textarea>

          <div
            class="animate-[fade-in-top_1s_ease-in-out_2.5s_both]"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            <button
              @click="onClickKirim"
              class="animate-bounce min-w-[75px] px-2 py-2 bg-[#958277] text-white rounded-lg hover:opacity-80 focus:outline-none active:outline-none text-base block mx-auto mb-4"
            >
              Kirim
            </button>
          </div>

          <img
            src="../../public/decoration-2.png"
            class="w-full mb-4 rotate-180"
          />

          <div
            class="p-2 max-h-[150px] shadow-lg rounded-lg border-[1px] border-[#CED4D9] bg-[#FFF9F6] flex flex-col w-[90%] mx-auto mb-4 font-sans"
            v-for="ucapan in ucapan"
            :key="ucapan.id"
            data-aos="zoom-in-up"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            <div class="flex justify-between text-sm items-center mb-2">
              <h1 class="text-xs font-bold capitalize">{{ ucapan.nama }}</h1>
              <span
                class="bg-[#958277] rounded-xl text-white text-[8px] px-1 py-[2px]"
                v-if="ucapan.konfirmasi === 'hadir'"
                ><i class="fas fa-check"></i> Hadir</span
              >
              <span
                class="bg-[#958277] rounded-xl text-white text-[8px] px-1 py-[2px] self-baseline"
                v-else
                ><i class="fas fa-times"></i> Tidak Hadir</span
              >
            </div>
            <div class="italic text-xs overflow-y-scroll w-full h-full">
              "{{ ucapan.ucapan }}"
            </div>
          </div>

          <div
            class="w-full flex justify-center items-center"
            data-aos="zoom-in-down"
            data-aos-duration="1500"
            data-aos-once="true"
          >
            <button
              class="py-[2px] px-4 bg-[#958277] border-r-2 rounded text-white text-center"
              :class="[index === offset / limit ? 'opacity-70' : '']"
              @click="index !== offset / limit ? clickNext(index * limit) : ''"
              v-for="(data, index) in Math.ceil(allUcapanLength / limit)"
              :key="index"
            >
              {{ index + 1 }}
            </button>
          </div>

          <img
            src="../../public/decoration-2.png"
            class="w-full mt-12 rotate"
          />

          <div class="mt-8">
            <h1
              class="text-center text-3xl mb-4 font-honey"
              data-aos="zoom-in-up"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              Dompet Digital
            </h1>

            <div
              class="mt-4 p-4 bg-[url('./pattern.jpg')] bg-contain rounded-lg shadow-lg shadow-slate-400"
              data-aos="zoom-in-down"
              data-aos-duration="1500"
              data-aos-once="true"
            >
              <img
                src="../assets/images/logo-bca.png"
                class="w-28 mx-auto mb-8"
                alt=""
              />
              <p class="text-center font-bold">119 127 1837</p>
              <p class="text-center text-xl">a/n Tiara Aristya</p>
            </div>
            <img
              src="../../public/decoration-2.png"
              class="w-full mt-8 rotate-180"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Modal from "../components/Modal.vue";
import Menu from "../components/Menu.vue";
import Loading from "../components/Loading.vue";
import axios from "axios";
import Swal from "sweetalert2";
import AOS from "aos";
import "aos/dist/aos.css";
import Countdown from "@chenfengyuan/vue-countdown";

export default {
  name: "Home",
  components: {
    Modal,
    Countdown,
    Menu,
    Loading,
  },
  data() {
    return {
      show: false,
      modal: true,
      muted: false,
      loading: false,
      undangan: this.$route.params.nama,
      list: [
        "btn-kata-pengantar",
        "btn-mempelai-wanita",
        "btn-mempelai-pria",
        "btn-dday",
        "btn-lokasi",
      ],
      offset: 0,
      limit: 5,
      ucapan: [],
      allUcapanLength: 0,
      // ? Data for Input
      nama: null,
      konfirmasi: null,
      ucap: null,
    };
  },
  methods: {
    clickOpen() {
      this.show = true;
      const audio = document.getElementById("audio");
      audio.play();
    },
    onClickMuted() {
      const audio = document.getElementById("audio");
      this.muted = !this.muted;
      audio.muted = this.muted;
    },
    async onClickKirim() {
      this.loading = true;
      const temp = await this.kirimUcapan();
      if (temp === 1) {
        this.offset = 0;
        this.allUcapanLength = await this.ucapanLength();
        this.ucapan = await this.loadUcapan();
        this.loading = false;
        Swal.fire({
          icon: "success",
          title: "Yeay!",
          html: `Ucapan & Do'a berhasil dikirim,<br> Terima Kasih`,
        });
      } else {
        this.loading = false;
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `Ucapan gagal dikirim!`,
        });
      }
    },
    async kirimUcapan() {
      const API_URL = "https://fueremi-hasura.herokuapp.com/v1/graphql";
      const API_HEADERS = {
        "Content-Type": "application/json",
        "x-hasura-admin-secret": "18032405",
      };

      const API_QUERY = `
      mutation MyMutation {
        insert_tiara_atar_wedding_ucapan(objects: {konfirmasi: "${this.konfirmasi}", nama: "${this.nama}", ucapan: "${this.ucap}"}) {
          affected_rows
        }
      }
      `;
      try {
        const data = await axios.post(
          API_URL,
          { query: API_QUERY },
          { headers: API_HEADERS }
        );
        return data.data.data.insert_tiara_atar_wedding_ucapan.affected_rows;
      } catch (error) {
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `${error}`,
        });
        return;
      }
    },
    async clickNext(number) {
      this.loading = true;
      this.offset = number;
      this.ucapan = await this.loadUcapan();
      this.loading = false;
    },
    async ucapanLength() {
      const API_URL = "https://fueremi-hasura.herokuapp.com/v1/graphql";
      const API_HEADERS = {
        "Content-Type": "application/json",
        "x-hasura-admin-secret": "18032405",
      };

      const API_QUERY = `
      query MyQuery {
        tiara_atar_wedding_ucapan_aggregate {
          aggregate {
            count
          }
        }
      }
      `;
      try {
        const data = await axios.post(
          API_URL,
          { query: API_QUERY },
          { headers: API_HEADERS }
        );
        return data.data.data.tiara_atar_wedding_ucapan_aggregate.aggregate
          .count;
      } catch (error) {
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `${error}`,
        });
        return;
      }
    },
    async loadUcapan() {
      const API_URL = "https://fueremi-hasura.herokuapp.com/v1/graphql";
      const API_HEADERS = {
        "Content-Type": "application/json",
        "x-hasura-admin-secret": "18032405",
      };

      const API_QUERY = `
      query MyQuery {
        tiara_atar_wedding_ucapan(offset: ${this.offset}, limit: ${this.limit}, order_by: {created_at: desc}) {
          ucapan
          nama
          konfirmasi
          id
          created_at
        }
      }
      `;
      try {
        const data = await axios.post(
          API_URL,
          { query: API_QUERY },
          { headers: API_HEADERS }
        );
        return data.data.data.tiara_atar_wedding_ucapan;
      } catch (error) {
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `${error}`,
        });
        return;
      }
    },
  },
  computed: {
    dday() {
      return (
        new Date("March 6, 2022 09:00:00").getTime() - new Date().getTime()
      );
    },
  },
  async created() {
    AOS.init();
    this.loading = true;
    this.ucapan = await this.loadUcapan();
    this.allUcapanLength = await this.ucapanLength();
    this.loading = false;
  },
  // watch: {
  //   modal() {
  //     if (this.modal === false) {
  //       var i = 0;
  //       setInterval(() => {
  //         if (i > 4) {
  //           i = 0;
  //           document.getElementById(this.list[i]).click();
  //           i++;
  //         } else {
  //           document.getElementById(this.list[i]).click();
  //           i++;
  //         }
  //       }, 5000);
  //     }
  //   },
  // },
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
