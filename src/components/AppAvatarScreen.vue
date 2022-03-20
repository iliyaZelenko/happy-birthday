<template>
  <div class="avatar-screen">
    <AppConfeti />

    <h1 class="name-text">
      <span style="--i:1">М</span>
      <span style="--i:2">о</span>
      <span style="--i:3">я</span>
      <span style="--i:4"> </span>
      <span style="--i:5">л</span>
      <span style="--i:6">ю</span>
      <span style="--i:7">б</span>
      <span style="--i:8">о</span>
      <span style="--i:9">в</span>
      <span style="--i:10">ь</span>
    </h1>

    <br>
    <br>
    <br>

    <div class="gradient-border">
      <img
        class="hat animate__animated animate__fadeIn animate__delay-2s"
        :src="require('@/assets/hat.svg')"
      >
      <img
        :src="require('@/assets/liza.jpg')"
        class="animate__animated animate__fadeIn animate__slow"
        alt="Liza image"
      >
    </div>

    <br>

    <div class="animate__animated animate__fadeIn animate__delay-2s">
      <div class="animate__animated animate__heartBeat animate__infinite">
        <div class="text-birthday">
          С днюхой!
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppConfeti from '@/components/AppConfeti.vue'

export default defineComponent({
  name: 'AppAvatarScreen',
  components: {
    AppConfeti
  },
  data () {
    return {
    }
  }
})
</script>

<style scoped lang="sass">
  .avatar-screen
    height: 100%

  .hat
    position: absolute
    z-index: 1
    width: 110px
    right: 35px
    top: -40px

  img
    width: 100%

  .gradient-border
    position: relative
    max-width: 65%
    margin: 0 auto
    z-index: -2
</style>

<style scoped lang="scss">
  .text-birthday {
    margin-top: 30px;
    font-weight: 600;
    font-size: 30px;
    letter-spacing: 10px;
    text-align: center;
    text-transform: uppercase;
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    background-size: 400%;
    animation: move 5s ease infinite;
    background-image: linear-gradient( 68.7deg,  rgba(29,173,235,1) 13.2%, rgba(137,149,250,1) 29.8%, rgba(229,109,212,1) 48.9%, rgba(255,68,128,1) 68.2%, rgba(255,94,0,1) 86.4% );
  }

  @keyframes move {
    0%,100%{
      background-position: 200% 0%;
    }

    50%{
      background-position: 0% 200%;
    }
  }

  /* Name effect */
  .name-text span {
    font-size: 20px;
    padding: 0 10px;
    text-transform: uppercase;
    color: #fff;
    animation: zoomup 2s linear infinite;
    animation-delay: calc(200ms * var(--i));
  }

  $color: red;

  @keyframes zoomup {
    0%,
    100% {
      color: $color;
      filter: blur(1px);
      text-shadow: 0 0 10px $color, 0 0 20px $color, 0 0 30px $color,
      0 0 40px $color, 0 0 60px $color, 0 0 80px $color, 0 0 100px $color,
      0 0 120px $color;
    }

    5%,
    95% {
      filter: blur(0);
      color: black;
      text-shadow: none;
    }
  }

  /* gradient */
  .gradient-border {
    --borderWidth: 8px;
    background: #1D1F20;
    position: relative;
    border-radius: var(--borderWidth);
  }
  .gradient-border:after {
    content: '';
    position: absolute;
    top: calc(-1 * var(--borderWidth));
    left: calc(-1 * var(--borderWidth));
    height: calc(100% + var(--borderWidth) * 2);
    width: calc(100% + var(--borderWidth) * 2);
    background: linear-gradient(60deg, #f79533, #f37055, #ef4e7b, #a166ab, #5073b8, #1098ad, #07b39b, #6fba82);
    border-radius: calc(2 * var(--borderWidth));
    z-index: -1;
    animation: animatedgradient 3s ease alternate infinite;
    background-size: 300% 300%;
  }

  @keyframes animatedgradient {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }
</style>
