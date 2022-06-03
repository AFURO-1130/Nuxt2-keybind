<template>
  <div>
    <h1>command + Shift押すとキンジョウくんのscarpboxが開きます(招待してある人限定で)</h1>
    <p>あとは、何のkeyを押したかが一目でわかるようになっています</p>
    <p>key: {{ key }}</p>
    <p>keyCode: {{ KeyCode }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
      key: '',
      KeyCode: '',
    }
  },
  mounted() {
    document.addEventListener('keydown', this.keyDown)
  },
  methods: {
    keyDown(e: any) {
      this.key = e.key
      this.KeyCode = e.keyCode
      if (e.metaKey) {
        if (e.key === 'Shift') {
          const url = 'https://scrapbox.io/kinjyo'
          window.open(url,'_blank')
        }
      }
    },
  },
})
</script>
