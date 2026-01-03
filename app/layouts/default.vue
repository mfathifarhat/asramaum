<script setup>
import { ref, onMounted, onUnmounted} from 'vue'
import IconMenu from '~/components/icons/IconMenu.vue'
import IconInstagram from '~/components/icons/IconInstagram.vue'
import IconTikTok from '~/components/icons/IconTikTok.vue'
import IconYoutube from '~/components/icons/IconYoutube.vue'

const hasScrolled = ref(false)

const handleScroll = () => {
  hasScrolled.value = window.scrollY > 100
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})


</script>

<template>
  <nav
    class="flex justify-between items-center p-3 bg-white/80 border-gray-300 backdrop-blur-sm z-50 px-8 md:px-16 fixed w-full"
    :class="{ 'border-b': hasScrolled }">
    <div class="size-12 rounded-full bg-white">
      <img src="~/assets/img/logo.png" class="size-12" alt="" />
    </div>


    <button class="md:hidden">
      <IconMenu class="size-8 text-black" />
    </button>

    <div class="hidden md:flex space-x-8 text-sm">
      <RouterLink to="/" class="font-semibold ">Beranda</RouterLink>
      <RouterLink to="/" class="font-semibold ">Tentang</RouterLink>
      <RouterLink to="/" class="font-semibold ">Fasilitas</RouterLink>
      <RouterLink to="/" class="font-semibold ">Blog</RouterLink>
      <RouterLink to="/" class="font-semibold ">Informasi & Layanan</RouterLink>
      <RouterLink to="/" class="font-semibold ">Kontak</RouterLink>
    </div>
  </nav>

  <div class=" pt-[72.8px]">
    <slot />
  </div>

  <footer class="border-t px-8 py-8 mt-8">
    <div class="max-w-7xl mx-auto flex flex-col items-center space-y-8">
      <div class="size-16 aspect-square rounded-full bg-white">
        <img src="~/assets/img/logo.png" class="w-full" alt="" />
      </div>

      <h4 class="text-lg font-semibold">Asrama Mahasiswa Universitas Negeri Malang</h4>

      <div class="flex-col md:flex-row  flex items-center md:justify-end space-x-0 md:space-x-8 md:space-y-0 space-y-6">
        <a href="" class="font-medium">Beranda</a>
        <a href="" class="font-medium">Tentang</a>
        <a href="" class="font-medium">Fasilitas</a>
        <a href="" class="font-medium">Blog</a>
        <a href="" class="font-medium">Informasi & Layanan</a>
        <a href="" class="font-medium">Kontak</a>
      </div>

      <div class="flex items-center space-x-6">
        <a href="" class="text-gray-500 hover:text-primary">
          <IconInstagram class="size-8" />
        </a>

        <a href="" class="text-gray-500 hover:text-primary">
          <IconTikTok class="size-8" />
        </a>

        <a href="" class="text-gray-500 hover:text-primary">
          <IconYoutube class="size-8" />
        </a>
      </div>

      <hr class="mt-4 w-full">

      <span>Copyright ©2025 Asrama Universitas Negeri Malang</span>
    </div>
  </footer>
</template>

<style scoped></style>
