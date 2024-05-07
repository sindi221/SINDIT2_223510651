<template>
  <div class="container">
    <header>
      <h1>{{ pageTitle }}</h1>
    </header>
    <main>
      <section class="hero">
        <h2>"Welcome to My Fragrance Website!"</h2>
        <p></p>
        <button @click="toggleModal">Learn More</button>
      </section>
      <section class="features">
        <div class="feature">
          <img src="./assets/P3-removebg-preview.png" alt="Feature 1" />
          <h3>
            ZARA <br />
            RED VANILLA
          </h3>
          <p>
            Wewangian canggih, hangat, dan rempah dengan aroma nuansa bunga dan rasa manis. Sebuah
            buket dari bunga iris dan botan merah elegan, dikombinasikan dengan kesegaran aroma
            jeruk keprok dan sentuhan rasberi yang manis dan lembut, menyatu dengan aroma vanili.
          </p>
        </div>

        <div class="feature">
          <img src="./assets/P4-removebg-preview.png" alt="Feature 2" />
          <h3>
            ZARA <br />
            Night Pour Homme II
          </h3>
          <p>
            Parfum Zara Night Pour Homme II ini memiliki campuran wangi buah bergamot, wangi amber
            (campuran aroma vanili, bunga dan aroma kayu) dan wangi lavender. Campuran wewangian
            tersebut menimbulkan rasa segar, nocturnal dan sporty.
          </p>
        </div>

        <div class="feature">
          <img src="./assets/P2-removebg-preview (1).png" alt="Feature 3" />
          <h3>
            ZARA <br />
            NUDE BOUQUET
          </h3>
          <p>
            Eau de parfum. Piramida wangi termasuk aroma ceri, peony, dan vanili. Merupakan aroma
            segar, nyaman, dan bersemangat.
          </p>
        </div>
      </section>
      <section class="testimonial">
        <blockquote>
          <p>"This perfume website is amazing! It has everything I need and more."</p>
          <footer>- "Fragrance Enthusiast Hub"</footer>
        </blockquote>
      </section>
    </main>
    <footer>
      <p>&copy; 2024 Our Website. SINDI MAHARANI.</p>
    </footer>
    <div class="modal" v-if="showModal">
      <div class="modal-content">
        <span class="close" @click="toggleModal">&times;</span>
        <h2>About Us</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
          ut labore et dolore magna aliqua.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageTitle: 'Welcome to Our Website!',
      showModal: false,
      isHighlighted: false,
      inputText: '',
      boxColor: 'lightblue',
      boxContent: 'Hover me to change color!',
      listItems: ['Item 1', 'Item 2', 'Item 3']
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    updateText(event) {
      this.inputText = event.target.value
    },
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted
    },
    changeColor() {
      const colors = ['lightblue', 'lightgreen', 'lightcoral', 'lightsalmon']
      const randomIndex = Math.floor(Math.random() * colors.length)
      this.boxColor = colors[randomIndex]
    }
  }
}
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

main {
  padding: 20px;
}

.hero {
  text-align: center;
  margin-bottom: 40px;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.2rem;
  margin-bottom: 30px;
}

.hero button {
  padding: 10px 20px;
  font-size: 1.2rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.features {
  display: flex;
  justify-content: space-around;
  margin-bottom: 40px;
}

.feature {
  text-align: center;
  flex: 1;
}

.feature img {
  max-width: 150px;
}

.feature h3 {
  margin-top: 20px;
  font-size: 1.5rem;
}

.testimonial {
  text-align: center;
  margin-bottom: 40px;
}

.testimonial blockquote {
  font-size: 1.5rem;
}

.testimonial footer {
  margin-top: 10px;
  font-style: italic;
}

footer {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
