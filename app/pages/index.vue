<script setup>
import { Button } from '@/components/ui/button';
import { Card, CardContent } from '@/components/ui/card'
import { Carousel, CarouselContent, CarouselItem, CarouselNext, CarouselPrevious } from '@/components/ui/carousel'

definePageMeta({
  layout: "default"
})
let penerimaan = false;
</script>

<template>
  <section id="main" class="items-center">
    <div class="py-5 text-center w-full bg-violet-500 text-white font-semibold" v-if="penerimaan">
      Penerimaan Warga Baru sudah dibuka!!!
    </div>
    <div class="flex flex-col items-center text-center px-4 p-16 mt-6 pb-8 md:pb-16">
      <h4 class="lg:text-lg">Selamat Datang di <b>Asrama Mahasiswa Universitas Negeri Malang</b></h4>
      <h1 class="text-3xl leading-12 md:text-4xl md:leading-15 mt-4 font-semibold">Tempatnya mahasiswa <br>
        <b class="font-semibold rounded-full text-violet-600">berproses, belajar, dan
          tumbuh
          bareng</b>.
      </h1>
      <p class="max-w-xl mt-6">
        Di sini, kamu nggak cuma tinggal, tapi juga jadi bagian dari komunitas yang solid, aktif, dan seru banget!
      </p>
    </div>

    <div class="py-8 px-4 max-w-7xl mx-auto">
      <div class="md:aspect-8/4 w-full rounded-4xl overflow-hidden">
        <img src="~/assets/img/hero-image.webp"
          class="w-full object-cover grayscale brightness-50 hover:grayscale-0 duration-250" alt="">
      </div>
    </div>
  </section>

  <!-- <div class="absolute w-6xl left-12 size-96 bg-green-100 top-70 blur-3xl -z-10"></div> -->

  <div class="py-16 px-4 max-w-7xl mx-auto">
    <div class="grid grid-cols-5 md:grid-cols-7 lg:grid-cols-9 items-center gap-5">
      <div class="col-span-2 md:col-span-3 lg:col-span-4">
        <div class="w-full h-0.5 bg-gray-300"></div>
      </div>
      <div class="flex justify-center">
        <div class="aspect-square size-15">
          <img src="~/assets/img/logo.png" class="w-full" alt="" />
        </div>
      </div>
      <div class="col-span-2 md:col-span-3 lg:col-span-4">
        <div class="w-full h-0.5 bg-gray-300"></div>
      </div>
    </div>
  </div>

  <section id="about" class="max-w-7xl mx-auto px-4 py-8 flex flex-col items-center ">
    <h1 class="text-2xl text-center font-bold">Tentang Asrama UM</h1>
    <p class="mt-4 md:max-w-3xl text-center text-gray-700">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis voluptatem, consectetur voluptates provident impedit
      aliquam aspernatur distinctio pariatur sit vel minima dignissimos eum enim error qui repudiandae quisquam, quo
      tenetur.</p>

    <Button class="mt-6" variant="">Baca Selengkapnya</Button>

    <div class="grid grid-cols-2 md:grid-cols-3 mt-12 gap-4 md:gap-8 items-stretch">
      <div class="col-span-2">
        <div class="h-full rounded-3xl overflow-hidden">
          <img src="~/assets/img/hero-image.webp"
            class="h-full object-cover grayscale brightness-50 hover:grayscale-0 duration-250" alt="">
        </div>
      </div>
      <div class="col-span-2 md:col-span-1">
        <div class="grid grid-cols-2 md:grid-cols-1 gap-4 md:gap-8">
          <div class="h-full rounded-3xl overflow-hidden">
            <img src="~/assets/img/hero-image.webp"
              class="w-full object-cover grayscale brightness-50 hover:grayscale-0 duration-250" alt="">
          </div>

          <div class="h-full rounded-3xl overflow-hidden">
            <img src="~/assets/img/hero-image.webp"
              class="w-full object-cover grayscale brightness-50 hover:grayscale-0 duration-250" alt="">
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="facility" class="max-w-7xl mx-auto px-4 py-8 flex flex-col pt-24 w-full">

    <h1 class="text-2xl font-bold">Fasilitas</h1>

    <Carousel class="w-full mt-4" :opts="{
      align: 'start',
    }">
      <div class="grid grid-cols-6 gap-6 mb-4">

        <div class="col col-span-full md:col-span-4">
          <p class="md:max-w-3xl text-gray-700 text-justify">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis voluptatem, consectetur voluptates provident
            impedit
            aliquam aspernatur distinctio pariatur sit vel minima dignissimos eum enim error qui repudiandae quisquam,
            quo
            tenetur.</p>
        </div>
        <div class="col col-span-2 hidden md:flex justify-end space-x-3">
          <CarouselPrevious size="icon-lg" />
          <CarouselNext />
        </div>
      </div>
      <CarouselContent>
        <CarouselItem v-for="(_, index) in 5" :key="index" class="md:basis-1/2 lg:basis-2/5">
          <div class="p-1">
            <Card>
              <CardContent class="flex aspect-square items-center justify-center p-6">
                <img src="~/assets/img/hero-image.webp" />
              </CardContent>
            </Card>
          </div>
        </CarouselItem>
      </CarouselContent>
    </Carousel>
  </section>


  <section id="blog" class="max-w-7xl mx-auto px-4 py-8 flex flex-col items-center pt-24 w-full">
    <h1 class="text-2xl font-bold text-center">Kehidupan Asrama</h1>

    <p class="mt-4 md:max-w-5xl text-center text-gray-700">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis voluptatem, consectetur voluptates provident impedit
      aliquam aspernatur distinctio pariatur sit vel minima dignissimos eum enim error qui repudiandae quisquam, quo
      tenetur.</p>


    <div class="grid grid-cols-1 md:grid-cols-3 gap-2 w-full my-6">
      <div class="col" v-for="i in 3">
        <a href="" class="w-full h-full p-5 hover:bg-gray-100 rounded-2xl flex flex-col space-y-2">
          <div class="w-full h-[300px] bg-violet-600 rounded-xl"></div>
          <div class="text-sm mt-2 text-gray-500">23 Agustus 2025</div>
          <h4 class="font-semibold line-clamp-1">Lorem ipsum dolor sit amet consectetur adipisicing</h4>
          <p class="line-clamp-2 text-sm text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing
            elit. Itaque id, aspernatur, inventore, eos molestias
            rem consequuntur voluptatum eligendi magnam sequi pariatur sunt provident. Vero est facere consequatur
            deserunt ad et?</p>
        </a>
      </div>
    </div>

    <Button>Lihat Lainnya</Button>
  </section>

  <section id="contact" class="max-w-7xl mx-auto px-4 py-8 flex flex-col items-center my-12 w-full text-white">
    <div class="bg-violet-500 rounded-xl w-full p-12 flex flex-col space-y-8 items-center">
      <h1 class="text-2xl font-bold text-center">Masih Punya Pertanyaan tentang Asrama UM?</h1>
      <p class="text-center max-w-4xl">Jika kamu masih memiliki pertanyaan seputar fasilitas, aturan, atau pendaftaran
        asrama, silakan hubungi kami untuk mendapatkan informasi resmi dan akurat.</p>
      <Button variant="secondary" class="font-semibold">Hubungi Kami</Button>
    </div>
  </section>
</template>


<style lang="scss" scoped></style>
