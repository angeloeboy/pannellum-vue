<template>
  <Navigation @onShowVidClicked="showVidFunc" @onShowQuizClicked="showQuizFunc"  @onShowFaqClicked="showFaqFunc"/>

  <transition name="fade">
    <VidComponent v-if="showVid" @onShowVidClicked="showVidFunc" />
  </transition>

  <transition name="fade">
    <QuizComponent v-if="showQuiz" @onShowQuizClicked="showQuizFunc" />
  </transition>

  <transition name="fade">
    <FaqComponent v-if="showFaq" @onShowFaqClicked="showFaqFunc" />
  </transition>


  <VuePannellum 
    :autoLoad="true"  
    :mouseZoom="false" 
    :doubleClickZoom="false" 
    :maxHfov="100" 
    :minHfov="100"
    style="height: 100vh; width: 100vw;"
    :src="img"
    :hotSpots="hotspots"
    :hotSpotsDebug="true"
    >
    
  </VuePannellum>
  <div class="playAudio">
     <audio class="audio-element" autoplay>
          <source :src="audio" /> 
      </audio>

      <button @click="toggleAudio">
        <p v-if="audioPlaying">Play Audio</p>
        <p v-else>Stop Audio</p>

      </button>
  </div>
</template>

<script>
import VuePannellum from 'vue-pannellum'
import img from "../assets/alma.jpg"
import Navigation from "./Navigation.vue"
import VidComponent from "./VidEmbed.vue"
import audio from "../assets/audio.mp3"
import QuizComponent from "./Quiz.vue"
import FaqComponent from "./Faq.vue"

export default {
  name: 'App',

  components: {
    VuePannellum,
    Navigation,
    VidComponent,
    QuizComponent,
    FaqComponent
  },

  data(){
    return{
      img: img,
      audio: audio,
      showVid: false,
      audioPlaying: true,
      showQuiz: false,
      showFaq: false,
      hotspots: [
        {
            "pitch": 13,
            "yaw": -43,
            "type": "custom",
            "cssClass": "custom-hotspot",
            "clickHandlerFunc": this.showVidFunc
        },
        {
            "pitch": 7,
            "yaw": -85,
            "type": "custom",
            "cssClass": "custom-hotspot",
            "clickHandlerFunc": this.showQuizFunc
        },

        {
            "pitch": 7,
            "yaw": -98,
            "type": "custom",
            "cssClass": "custom-hotspot",
            "clickHandlerFunc": this.showFaqFunc
        }

      ]
    }
  },

  methods: {
    showVidFunc() {
      this.showVid = !this.showVid
    },

    toggleAudio(){
      const audioEl = document.getElementsByClassName("audio-element")[0];
      this.audioPlaying = !this.audioPlaying

      if(this.audioPlaying){
        audioEl.pause()
        
      }else{
        audioEl.play()
      }

    },

    showQuizFunc(){
      this.showQuiz = !this.showQuiz
    },

    showFaqFunc(){
      this.showFaq = !this.showFaq
      console.log("func")
    }
  },
  
  mounted(){
    this.toggleAudio();
  }
}
</script>

<style>

.fade-enter{
  transition: all 0.5s;
  transform: translateY(-20%);
  opacity: 0;
}

.fade-enter-active{
  transition: opacity 0.5s;
  opacity: 1;
  transform: translateY(0%);
  opacity: 1;
}


.fade-leave-active{
  transition: all 0.3s;
  opacity: 0;
  transform: translateY(-20%);

}

.playAudio{
  position: absolute;
  top: 20px;
  left: 20px;
}

.playAudio button{
  padding: 10px 15px;
  background-color: black;
  border: none;
  color: white;
}


.custom-hotspot {
    height: 50px;
    width: 50px;
    z-index: 99999;
    visibility: visible;
    background-image: url("../assets/up-arrow.svg");
    background-size: cover;
}

/* div.custom-tooltip{
  background-color: red;
} */

</style>