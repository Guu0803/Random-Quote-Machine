<template>
  <div class="window">
    <div v-if="quote" class="quote-box">
      <div class="quote-text">
        <i class="fa-solid fa-quote-left"></i> {{ quote.quote }}
      </div>
      <p>- {{ quote.author }}</p>
      <div class="container-button-social-media">
        <div class="container-social-media">
          <a
            href="https://twitter.com/i/flow/login?input_flow_data=%7B%22requested_variant%22%3A%22eyJsYW5nIjoicHQifQ%3D%3D%22%7D">
            <i class="fa-brands fa-twitter social"></i></a>
          <a href="https://www.tumblr.com/?language=pt_BR">
            <i class="fa-brands fa-tumblr social"></i> </a>
        </div>
        <button @click="newQuote()">
          New Quote
        </button>
      </div>
    </div>
    <div class="name">By Gustavo Nogueira</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: {}
    }

  },
  methods: {
    newQuote() {
      const axios = require('axios')
      let url = 'https://api.api-ninjas.com/v1/quotes?category='
      let header = {
        'X-Api-Key': 'e93dN1hsMhkYy4sjXk8r3w==goGEqhMwjfLmuQns',
      }
      let config = { headers: header }
      axios.get(url, config).then(response => {
        this.quote = response.data[0]
        let randomColor = `${this.randomNumber(0, 255)}, ${this.randomNumber(0, 255)}, ${this.randomNumber(0, 255)}`;
        document.documentElement.style.setProperty('--rgb', `rgb(${randomColor})`);
        document.documentElement.style.setProperty('--rgbHover', `rgba(${randomColor}, 0.8)`);
      })

    },
    randomNumber(min, max) {
      return Math.floor(Math.random() * (max - min))
    }
  },
  created() {
    this.newQuote()
  }

}

</script>
<style>
:root {
  --rgb: ;
  --rgbHover: ;
}

body {
  margin: 0;
  padding: 0;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.window {
  width: 100vw;
  height: 100vh;
  background-color: var(--rgb);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  transition: 300ms ease-in-out;
}

.quote-box {
  width: 40vw;
  height: auto;
  background-color: white;
  border-radius: 5px;
  padding: 1.5vw;
  box-sizing: border-box;
  transition: 300ms ease-in-out;
}

.quote-text {
  font-size: 1.5em;
  color: var(--rgb);
  transition: 300ms ease-in-out;
  
}

p {
  display: flex;
  justify-content: flex-end;
  width: 100%;
  color: var(--rgb);
  transition: 300ms ease-in-out;

}

.container-social-media {
  display: flex;
  align-items: center;
  gap: 1vw;
}

.container-button-social-media {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 5vh;
}

a {
  font-size: 1.7em;
  background-color: var(--rgb);
  width: 2em;
  text-align: center;
  padding: 0.5vh 0;
  border-radius: 5px;
  color: white;
}

button {
  border: none;
  font-size: 1.2em;
  background-color: var(--rgb);
  border-radius: 5px;
  height: 100%;
  color: white;
  cursor: pointer;
}

a:hover,
button:hover {
  background-color: var(--rgbHover);
}
.name {
  margin-top: 3vh;
  color: white;
}
</style>
