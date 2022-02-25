<template>
  <div
    class="w-screen h-screen font-akaya flex justify-center items-center flex-col p-6"
    v-if="!login"
  >
    <h1 class="font-honey text-4xl text-center mb-8 text-[#958277]">Login</h1>
    <input
      type="text"
      placeholder="Username ..."
      class="border-[1px] border-[#958277] rounded-md py-2 px-1 mb-4 text-xs w-48 text-[#958277] focus:border-none"
      v-model="username"
    />
    <input
      type="password"
      placeholder="Password ..."
      class="border-[1px] border-[#958277] rounded-md py-2 px-1 mb-4 text-xs w-48 text-[#958277]"
      v-model="password"
    />
    <button
      @click="onClickLogin"
      class="animate-bounce min-w-[75px] px-2 py-2 bg-[#958277] text-white rounded-lg hover:opacity-80 focus:outline-none active:outline-none text-xs block mx-auto mb-4"
    >
      Kirim
    </button>
  </div>

  <div
    class="w-screen h-screen font-akaya flex justify-center items-center flex-col p-6 text-[#958277]"
    v-if="login"
  >
    <h1 class="text-2xl mb-6">Undangan Otomatis (Whatsapp)</h1>
    <input
      type="text"
      v-model="noWA"
      placeholder="No. Whatsapp ..."
      class="border-[1px] border-[#958277] rounded-md py-2 px-1 mb-4 text-xs w-48 text-[#958277]"
    />
    <input
      type="text"
      v-model="nama"
      placeholder="Nama ..."
      class="border-[1px] border-[#958277] rounded-md py-2 px-1 mb-4 text-xs w-48 text-[#958277]"
    />
    <!-- `https://wa.me/${this.noWA}?text=Assalamualaikum%20Wr.%20Wb.%0A%0AKami%20ingin%20mengundang%20anda%20untuk%20menghadiri%20pernikahan%20kami%0A%0Ahttps://tiara-atar-wedding.netlify.app/${temp}`,
        "_blank" -->
    <a
      @click.prevent="onClickKirim"
      target="_blank"
      class="animate-bounce min-w-[75px] px-2 py-2 bg-[#958277] text-white rounded-lg hover:opacity-80 focus:outline-none active:outline-none text-xs block mx-auto mb-4"
    >
      Kirim Undangan
    </a>
  </div>
</template>

<script>
import Swal from "sweetalert2";

export default {
  name: "Invitation",
  data() {
    return {
      login: false,
      username: null,
      password: null,
      noWA: "+628",
      nama: "",
      link: null,
    };
  },
  methods: {
    onClickKirim() {
      this.nama = this.nama.replace(/ /g, ".").replace("&", "=");
      window.open(
        `https://wa.me/${this.noWA.replace(
          /[^a-zA-Z 0-9+]+/g,
          ""
        )}?text=Assalamualaikum%20Wr.%20Wb.%0A%0AKami%20ingin%20mengundang%20anda%20untuk%20menghadiri%20pernikahan%20kami%0A%0Ahttps://tiara-atar-wedding.netlify.app/${
          this.nama
        }`,
        "_blank"
      );
      this.nama = "";
      this.noWA = "+628";
    },
    onClickLogin() {
      if (this.username === null || this.password === null) {
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `Silahkan isi username dan password`,
        });
        return;
      } else if (
        this.username.toLowerCase() === "atartiara" &&
        this.password === "06032022"
      ) {
        Swal.fire({
          icon: "success",
          title: "Yeay...",
          text: `Selamat datang Kak Ara dan Bang Atar`,
        });
        this.login = true;
      } else {
        Swal.fire({
          icon: "error",
          title: "Oops...",
          text: `Salah Password`,
        });
        this.password = null;
      }
    },
  },
};
</script>
