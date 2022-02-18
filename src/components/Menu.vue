<template>
  <nav
    class="fixed bottom-5 left-1/2 w-[90%] rounded-full -translate-x-[50%] bg-[#958277] z-49 shadow-lg"
  >
    <div class="flex justify-evenly items-center gap-2 px-2">
      <a class="my-2 p-1 rounded-ful" href="#kata-pengantar" v-smooth-scroll>
        <img
          src="@/assets/images/menu-1.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
      <a class="my-2 p-1 rounded-ful" href="#mempelai-wanita" v-smooth-scroll>
        <img
          src="@/assets/images/menu-2.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
      <a class="my-2 p-1 rounded-ful" href="#mempelai-pria" v-smooth-scroll>
        <img
          src="@/assets/images/menu-2.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
      <a class="my-2 p-1 rounded-ful" href="#dday" v-smooth-scroll>
        <img
          src="@/assets/images/menu-3.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
      <a class="my-2 p-1 rounded-ful" href="#lokasi" v-smooth-scroll>
        <img
          src="@/assets/images/menu-5.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
      <a class="my-2 p-1 rounded-ful" href="#couple" v-smooth-scroll>
        <img
          src="@/assets/images/menu-4.png"
          class="h-[40px] w-[40px]"
          alt=""
        />
      </a>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Menu",
};
</script>
