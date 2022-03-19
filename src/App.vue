<template>
  <div id="app">
    <Header />
    <div class="container">
      <div v-if="error">
        <p class="log-warning">{{ error }}</p>
      </div>
      <div v-else>
        <ul class="reference-listing">
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Home-160121-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Home-160121-454x692.jpg" alt="Maquette Accueil : Le Petit Marché de Fred" loading="lazy">
            </a>
            <a href="https://www.lepetitmarchedefred.fr" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/lance-immo_accueil_V02-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/lance-immo_accueil_V02-454x699.jpg" alt="Maquette Accueil : Lance-Immo" loading="lazy">
            </a>
            <a href="https://www.lance-immo.fr" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Inolya-Intranet_Accueil_V01_B-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Inolya-Intranet_Accueil_V01_B-454x671.jpg" alt="Maquette Accueil : Intranet Inolya" loading="lazy">
            </a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Home-Final-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Home-Final-454x688.jpg" alt="Maquette Accueil : SMD Perffusion" loading="lazy">
            </a>
            <a href="https://www.smd-perfusion.fr" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2019/10/Saint-Andre-sur-Orne_Accueil_V02-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2019/10/Saint-Andre-sur-Orne_Accueil_V02-454x664.jpg" alt="Maquette Accueil : Saint André sur Orne" loading="lazy">
            </a>
            <a href="https://www.saint-andre-sur-orne.com" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Accueil.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/Accueil-454x445.jpg" alt="Maquette Accueil : Cap West" loading="lazy">
            </a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/SBV_V01-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/SBV_V01-454x1862.jpg" alt="Maquette Accueil : SBV" loading="lazy">
            </a>
            <a href="https://www.sbvbihel.fr" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        <li class="reference__item">
            <a href="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/SBTP-V02-scaled.jpg" class="reference__img-wrapper">
              <img class="reference__img" src="http://louanne-roger.fr/projet/wp-content/uploads/2021/07/SBTP-V02-454x1524.jpg" alt="Maquette Accueil : SBTP Bihel" loading="lazy">
            </a>
            <a href="https://www.sbtpbihel.com" target="_blank" rel="noopener" class="reference__lien">Lien vers le site en ligne</a>
        </li>
        </ul>
        <ul>
          <li v-for="jeu in jeux" :key="jeu.id">
            {{ jeu.attributes.name }}
          </li>
        </ul>
        <form id="form" v-on:submit="handleSubmit">
          <label for="name">Name</label>
          <input id="name" v-model="modifiedData.data.name" type="text" name="name">

          <label for="description">Description</label>
          <input id="description" v-model="modifiedData.data.description" type="text" name="description">

          <input type="submit" value="Submit">
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Header from "./components/Header"

export default {
  name: 'App',
  components: {
		Header
	},
  data () {
    return {
      jeux: [],
      modifiedData: {
        data: {
          name: '',
          description: '',
        },
      },
      error: null
    }
  },
  async mounted () {
    try {
      const response = await axios.get('http://145.239.198.154:1337/api/jeux')
      this.jeux = response.data.data
    } catch (error) {
      this.error = error;
    }
  },
  methods: {
    handleSubmit: async function(e) {
      e.preventDefault();
      try {
        const response = await axios.post('http://145.239.198.154:1337/api/jeux', this.modifiedData, {
        headers: {
          Authorization:
            'Bearer 10d2330bd8506f357c95a619e64ac8fc4ed2e86e956f08228abad1c5a9bf38dea7f87066b5b947cd81008e1d4e12b6534754f13411369a9e43967dd5e9871806f8fbb2424bae4e61d8f32df2719feea77fb0d624e1c1ae4d670750964d4cc1ab0a005e4d02553b13a6b1c71383878c943e1c385588d0eff52ba0cd0ad4e20f87',
        },
      })
        console.log(response);
      } catch(error) {
        this.error = error;
      }
    }
  }
}
/*

// LIGHTGALLERY
$('.reference-listing').lightGallery({
  selector: '.reference__img-wrapper',
  thumbnail:true,
  hash:false,
  share:false,
  autoplayControls:false,
  actualSize:false,
});

*/
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Signika:wght@300;400;500;600;700&display=swap');

*,
*::before,
*::after {
  box-sizing: inherit;
}

html {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  line-height: 1.15;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  font-smoothing: antialiased;
  -webkit-box-sizing:border-box;
  box-sizing:border-box;
  font-family: 'Signika', sans-serif;
}

body {
  background-image: url('./assets/fond.svg');
  background-attachment: fixed;
  scroll-behavior: smooth;
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  font-size: 1.0rem;
}

::selection {
  color: #fff;
}

::-moz-selection {
  color: #fff;
}

::selection {
  background-color: rgba(1, 85, 124, 0.5);
}

::-moz-selection {
  background-color: rgba(1, 85, 124, 0.5);
}

.container {
  max-width: 928px;
  margin: auto;
}

.log {
  border: 1px solid #403F56;
  color: #403F56;
  background-color: hsl(243, 15%, 95%);
  border-radius: 4px;
  padding: 8px 10px 8px 42px;
  margin-top: 10px;
  background-image: url("data:image/svg+xml,%3Csvg width='21' height='21' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M10.002 0c5.523 0 10.001 4.478 10.001 10.002 0 5.523-4.478 10.001-10.001 10.001C4.478 20.003 0 15.525 0 10.002 0 4.478 4.478 0 10.002 0Zm-.004 8.25a1 1 0 0 0-.993.885l-.007.116.004 5.502.007.116a1 1 0 0 0 1.986 0l.007-.117-.004-5.502-.006-.117a1 1 0 0 0-.994-.882Zm.004-3.749a1.252 1.252 0 1 0 0 2.503 1.252 1.252 0 0 0 0-2.503Z' fill='%23403F56'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: 10px 8px;
  background-size: 22px;
}

.log-warning {
  border: 1px solid hsl(43, 100%, 40%);
  color: hsl(43, 100%, 40%);
  background-color: #FFF8E6;
  border-radius: 4px;
  padding: 8px 10px 8px 42px;
  margin-top: 10px;
  background-image: url("data:image/svg+xml,%3Csvg width='26' height='25' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M24.767 21.134 14.243 1.171a1.956 1.956 0 0 0-3.48 0L.239 21.134c-.517.982-.157 2.206.804 2.734.287.158.607.24.934.241h21.05c1.091 0 1.976-.903 1.976-2.018 0-.334-.081-.663-.236-.957Zm-12.264-.115c-.682 0-1.235-.565-1.235-1.262 0-.697.553-1.261 1.235-1.261s1.235.565 1.235 1.261c0 .697-.553 1.262-1.235 1.262ZM13.844 8.33l-.354 7.695a.999.999 0 0 1-.988 1.01.999.999 0 0 1-.988-1.01l-.355-7.692c-.032-.756.541-1.396 1.282-1.43h.059c.742-.001 1.343.612 1.343 1.37l-.001.061.002-.004Z' fill='%23FDC947'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: 10px 8px;
  background-size: 22px;
}

.log-positif {
  border: 1px solid #22977E;
  color: #22977E;
  background-color: hsl(167, 63%, 92%);
  border-radius: 4px;
  padding: 8px 10px 8px 42px;
  margin-top: 10px;
  background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 1C5.925 1 1 5.925 1 12s4.925 11 11 11 11-4.925 11-11S18.075 1 12 1Zm4.768 9.14a1 1 0 1 0-1.536-1.28l-4.3 5.159-2.225-2.226a1 1 0 0 0-1.414 1.414l3 3a1 1 0 0 0 1.475-.067l5-6Z' fill='%2322977E'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: 10px 8px;
  background-size: 22px;
}

.log-negatif {
  border: 1px solid #FF0033;
  color: #FF0033;
  background-color: hsl(348, 100%, 92%);
  border-radius: 4px;
  padding: 8px 10px 8px 42px;
  margin-top: 10px;
  background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg clip-path='url(%23a)'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M4.222 4.222c-4.296 4.296-4.296 11.26 0 15.556 4.296 4.296 11.26 4.296 15.556 0 4.296-4.296 4.296-11.26 0-15.556-4.296-4.296-11.26-4.296-15.556 0Zm11.314 9.9a1 1 0 1 1-1.415 1.414L12 13.414l-2.121 2.122a1 1 0 1 1-1.415-1.415L10.586 12 8.464 9.879A1 1 0 1 1 9.88 8.464L12 10.586l2.121-2.122a1 1 0 1 1 1.415 1.415L13.414 12l2.122 2.121Z' fill='%23F03'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='a'%3E%3Cpath fill='%23fff' d='M0 0h24v24H0z'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: 10px 7px;
  background-size: 22px;
}

.reference-listing {
  display: flex;
  flex-wrap: wrap;
  padding: 0;
  margin: 0 -10px;
  list-style: none;
}

.reference__item {
  width: calc(50% - 20px);
  margin: 0 10px 20px 10px;
  background-color: rgba(0,0,0,0.6);
  border-radius: 4px;
  overflow: hidden;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 5px 15px;
}

@supports (backdrop-filter: blur(10px)) {
	/* IF backdrop-filter IS SUPPORTED */
	.reference__item {
    background-color: rgba(255,255,255,0.1);
    backdrop-filter: blur(10px);
	}
}

.reference__img-wrapper {
  position: relative;
  display: block;
  width: 100%;
  height: 0;
  padding-bottom: 70%;
  overflow: auto;
  border-radius: 4px;
}

.reference__img-wrapper:hover::after {
  opacity: 1;
}

.reference__img-wrapper::after {
  content: '';
  position: sticky;
  top: 10px;
  right: 10px;
  display: block;
  width: 40px;
  height: 40px;
  border-radius: 100%;
  margin: 0 0 0 auto;
  background-color: rgba(0,0,0,0.25);
  background-image: url("data:image/svg+xml,%3Csvg fill='none' xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M4 11a7 7 0 1 1 14 0 7 7 0 0 1-14 0zm7-9a9 9 0 1 0 5.618 16.032l3.675 3.675a1 1 0 0 0 1.414-1.414l-3.675-3.675A9 9 0 0 0 11 2zm1 6a1 1 0 1 0-2 0v2H8a1 1 0 1 0 0 2h2v2a1 1 0 1 0 2 0v-2h2a1 1 0 1 0 0-2h-2V8z' fill='%23fff'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 20px;
  transition: all 0.2s ease;
  opacity: 0;
}

@supports (backdrop-filter: blur(10px)) {
	/* IF backdrop-filter IS SUPPORTED */
	.reference__img-wrapper::after {
    backdrop-filter: blur(10px);
	}
}

/* Hide scrollbar for Chrome, Safari and Opera */
.reference__img-wrapper::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.reference__img-wrapper {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}

.reference__img {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: block;
  width: 100%;
}

.reference__lien {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  text-align: center;
  color: #FFF;
  line-height: 1;
  padding: 12px 10px;
}

.reference__lien:hover {
  opacity: 0.6;
  color: #FFF;
}

.reference__lien::after {
  content: '';
  display: inline-block;
  width: 15px;
  height: 15px;
  background-image: url("data:image/svg+xml,%3Csvg fill='none' xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M5 6a1 1 0 0 1 1-1h4a1 1 0 1 0 0-2H6a3 3 0 0 0-3 3v12a3 3 0 0 0 3 3h12a3 3 0 0 0 3-3v-4a1 1 0 1 0-2 0v4a1 1 0 0 1-1 1H6a1 1 0 0 1-1-1V6zm10-3a1 1 0 1 0 0 2h2.586l-6.293 6.293a1 1 0 0 0 1.414 1.414L19 6.414V9a1 1 0 1 0 2 0V4a1 1 0 0 0-1-1h-5z' fill='%23fff'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-left: 5px;
}

/* ////////////////////////////////////////////////////////////////////////////

  RESPONSIVE

//////////////////////////////////////////////////////////////////////////// */

/* ------------------------------------------- 
MAX-WIDTH 1200px
------------------------------------------- */
@media (max-width:1200px) {
  .container {
    width: 100%;
    padding: 0 10px;
  }
}

/* ------------------------------------------- 
MAX-WIDTH 1200px
------------------------------------------- */
@media (max-width: 801px) {
  .reference__item {
    width: calc(100% - 20px);
  }
}

</style>