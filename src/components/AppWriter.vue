<template>
  <div>
    <VueWriter
      :array='arr'
      :typeSpeed="100"
      :eraseSpeed="40"
    />

    <br>
    <br>
    <AppBtn v-if="show" @click="$emit('next')">
      Дальше
    </AppBtn>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// eslint-disable-next-line @typescript-eslint/ban-ts-comment
// @ts-ignore
import VueWriter from 'vue-writer'
import AppBtn from '@/components/AppBtn.vue'

export default defineComponent({
  name: 'AppWriter',
  components: {
    VueWriter,
    AppBtn
  },
  data () {
    return {
      show: false,
      arr: [
        'Я тебя очень люблю, солнышко!',
        'И это максимально искренние слова',
        'Так и есть, не сомневайся в этом',
        'Это просто так из меня не убрать',
        'Всё потому что с тобой было пережито очень много!',
        'Столько всего...',
        'Как ни с кем за всю жизнь.',
        'И дальше можно пережить ещё больше всего.',
        'Пережить того что можно только с близким человеком как ты',
        'Который очень тебя любит и готов за ради тебя на многое',
        'Настоящая любовь только один раз. Мне так кажется.'
      ]
    }
  },
  mounted () {
    setTimeout(() => {
      this.show = true
    }, 40000)
  }
})
</script>

<style>
.is-typed {
  font-size: 1.5rem;
}

.is-typed span.typed {
  color: black;
}

.is-typed span.cursor {
  display: inline-block;
  width: 3px;
  background-color: black;
  animation: blink 1s infinite;
}

.is-typed span.underscore {
  display: inline-flex;
  width: 10px;
  height: 1px;
  align-items:flex-end;
  background-color: black;
  animation: blink 1s infinite;
}

.is-typed span.cursor.typing {
  animation: none;
}

@keyframes blink {
  49% {
    background-color: black;
  }
  50% {
    background-color: transparent;
  }
  99% {
    background-color: transparent;
  }
}
</style>
