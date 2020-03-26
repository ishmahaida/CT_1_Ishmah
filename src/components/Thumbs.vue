<template>
   <div class="w-1/2">
    <div>
      <div class="flex flex-col mx-auto w-1/3" >
        <h1 class='text-center text-3xl'>Gallery Photo</h1>
        <div class="row">
          <div class='my-4 flex left'>
            <label>Judul</label>
            <input class='border' type="text" v-model='title'>
          </div>
          <div class='my-4 flex justify-between'>
            <label>Deksripsi</label>
            <input class='border' type="text" v-model='deskripsi'>
          </div>
          <div class='my-4 flex justify-between'>
            <label>Url</label>
            <input class='border' type="text" v-model='url'>
          </div>
          <div class='my-4 w-full flex justify-center'>
            <button @click="masukanGambar" class='border bg-blue-500 text-white p-2'>Submit</button>
          </div>
        </div>
      </div>

      <div v-if="gallery.length >= 1" class="w-1/2 mx-auto my-4 py-4 flex justify-center flex-col flex items-center text-center border relative">
        <h1 class='text-center text-3xl'>Hasilnya</h1>
        <div class="row">
          <img :src="gallery[index].url" width="600px" height="350px">
          <div>Title    :{{gallery[index].title}}</div>
          <div>Deksripsi:{{gallery[index].deskripsi}}</div>
        </div>
        <div class='absolute left-0 w-full flex justify-between'>
          <button @click='prev' class='border bg-blue-500 text-white p-2 rounded'>Prev</button>
          <button @click='next' class='border bg-blue-500 text-white p-2 rounded'>Next</button>
        </div>
      </div>

      <div v-if="gallery.length >= 1" class="w-1/2 mx-auto flex flex-wrap items-center justify-center">
        <div v-for='(gambar,ind) in gallery' :key='ind' class='mx-2 w-1/4 flex flex-col items-center' @click='index = ind'>
          <img :src="gambar.url" width="200px" height="100px">
          <div>Title  :{{gambar.title}}</div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {

  data () {
    return {
      gallery: [],
      title: '',
      deskripsi: '',
      url: '',
      index: 0
    }
  },
  methods: {
    masukanGambar () {
      var obj = {
        'title'     : this.title,
        'deskripsi' : this.deskripsi,
        'url'       : this.url
      }
      if (this.title && this.deskripsi && this.url) {
        this.gallery.push(obj)
        this.title = ''
        this.deskripsi = ''
        this.url = ''
      } else {
        alert ( 'Ada data kosong')
      }
    },
    next () {
      if (this.index < (this.gallery.length() - 1)) {
        this.index++
      }
    },
    prev () {
      if (this.index > 0) {
        this.index--
      }
    }
  }
}
</script>

<style>
</style>
