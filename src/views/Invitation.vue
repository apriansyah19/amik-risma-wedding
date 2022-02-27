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
    <h1 class="text-2xl mb-6">Undangan Otomatis</h1>

    <small class="text-red-500 mb-2"
      >*harus masukkan nomor WA untuk kirim by WA</small
    >
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

    <div id="code-snippet" style="display: none"></div>

    <button
      :disabled="noWA === '+628' || noWA.length <= 10"
      @click.prevent="onClickKirimWA"
      class="animate-bounce min-w-[75px] px-2 py-2 bg-[#958277] text-white rounded-lg hover:opacity-80 focus:outline-none active:outline-none text-xs block mx-auto mb-4 disabled:opacity-50"
    >
      Kirim Undangan (WA Personal Only)
    </button>

    <button
      @click.stop.prevent="onClickKirimIG"
      class="animate-bounce min-w-[75px] px-2 py-2 bg-[#958277] text-white rounded-lg hover:opacity-80 focus:outline-none active:outline-none text-xs block mx-auto mb-4"
    >
      Kirim Undangan (IG & WA Group)
    </button>
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
      igDM: null,
    };
  },
  methods: {
    onClickKirimWA() {
      this.nama = this.nama.replace(/ /g, ".").replace("&", "=");
      window.open(
        `https://wa.me/${this.noWA.replace(
          /[^a-zA-Z 0-9+]+/g,
          ""
        )}?text=Bismillahirrahmanirrahim%0A%0AAssalamualaikum%20Wr.%20Wb.%0ATanpa%20mengurangi%20rasa%20hormat,%20perkenankan%20kami%20mengundang%20Bapak/Ibu/Saudara/i,%20teman%20sekaligus%20sahabat,%20untuk%20menghadiri%20acara%20pernikahan%20kami:%0A%0Aapt.%20Tiara%20Aristya,%20S.Farm.%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20dan%0AAtar%20Satria%20Fikri,%20S.E.,%20M.%20Ak%0A%0AGedung%20UIN%20Sulthan%20Thaha%20Saifuddin%0AMinggu,%206%20Maret%202022%0A%0ABerikut%20link%20undangan%20kami%20untuk%20info%20lengkap%20dari%20acara%20bisa%20kunjungi:%0A%0Ahttps://tiara-atar-wedding.netlify.app/${
          this.nama
        }%0A%0AMerupakan%20suatu%20kebahagiaan%20bagi%20kami%20apabila%20Bapak/Ibu/Saudara/i%20berkenan%20untuk%20hadir%20dan%20memberikan%20doa%20restu%0A%0ATerima%20kasih%0AWassalamu'alaikum%20Wr.%20Wb.`,
        "_blank"
      );
      this.nama = "";
      this.noWA = "+628";
    },
    onClickKirimIG() {
      this.nama = this.nama.replace(/ /g, ".").replace("&", "=");
      this.igDM = `Bismillahirrahmanirrahim
      
Assalamualaikum Wr. Wb.
Tanpa mengurangi rasa hormat, perkenankan kami mengundang Bapak/Ibu/Saudara/i, teman sekaligus sahabat, untuk menghadiri acara pernikahan kami:
      
apt. Tiara Aristya, S.Farm.
          dan
Atar Satria Fikri, S.E., M. Ak 
                 
Gedung UIN Sulthan Thaha Saifuddin 
Minggu, 6 Maret 2022 
                 
Berikut link undangan kami untuk info lengkap dari acara bisa kunjungi: 
                 
https://tiara-atar-wedding.netlify.app/${this.nama} 
                 
Merupakan suatu kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan untuk hadir dan memberikan doa restu 
                 
Terima kasih 
Wassalamu'alaikum Wr. Wb.
`;

      const mySmartTextarea = document.createElement("textarea");
      mySmartTextarea.innerHTML = this.igDM;
      document.body.appendChild(mySmartTextarea);

      mySmartTextarea.select();
      document.execCommand("copy");
      Swal.fire({
        icon: "success",
        title: "Yeay...",
        html: `Undangan berhasil di copy ke clipboard <br> Silahkan tempel (paste) ke IG DM/ WA Group`,
      });
      // parentElement.removeChild(mySmartTextarea);

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
