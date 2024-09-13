
<template>
  <h1>Dzakwan Adiyatma Aryasuta- 233140701111009</h1>
  <!-- Click Counter -->
  <div id="app">
      <h2>Click Counter</h2>
      <p>Kamu telah menekan tombol {{ count }} kali.</p>
      <button @click="incrementCount">Tekan tombol</button>
      <button @click="() => count = 0">Reset</button>
  </div>
  
  <br>
  <!-- Box color changer -->
    <div class="box" v-bind:class="{ bluClass: bgColor }">
      <h1>Box color changer</h1>
      <p>Tekan tombol untuk mengganti warna Box nya</p>
      <button v-on:click="bgColor = !bgColor">Click</button>
    </div>
    <br>
    <!-- image carousel -->
  
    <div class="carousel-section">
        <img :src="images[currentImage]" class="carousel-image" />
        <p>
        <button @click="prevImage">Sebelum</button>
        <button @click="nextImage">Sesudah</button>
      </p>
    </div>
  </template>
  
  <script>
  export default {
    data: function() {
      return {
        // Untuk Klik Counter
        count: 0,
        text: "",
        // Untuk box color
        bgColor: false,
        // Untuk image carousel
        images: [ 
        'src/assets/a.png',
        'src/assets/b.jpg',
        'src/assets/c.jpg'
      ],
    currentImage: 0
      };
    },
  
    methods: {
      // Methods click counter
      incrementCount: function() {
        this.count++;
      },
      // Methods Untuk Image Carousel
  prevImage() {
    if (this.currentImage > 0) {
      this.currentImage--;
    } else {
      this.currentImage = this.images.length - 1;
    }
  },

  nextImage() {
      if (this.currentImage < this.images.length - 1) {
        this.currentImage++;
      } else {
        this.currentImage = 0;
      }
    }
    }
  };
  
  </script>
  
  <style>
  #app {
    font-family: "Times New Roman", Times, serif;
    text-align: center;
    color: #2c3e50;
    margin: 0 auto ;
  }
  
  .bluClass {
    background-color: rgb(0,191,255);
  }
  .box {
    text-align: center;
    padding: 20px;
    border: solid black 1px;
    width: 250px;
    margin: 0 auto;
  }

  .carousel-section {
    margin: 0 auto;
  }

  .carousel-image {
    width: 800px;
    height: 550px;
    margin: 30px 0;
    border: 4px solid #180606; 
    border-radius: 1px; 
  }
  </style>