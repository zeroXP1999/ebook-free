<template>
  <div>
    <div id="read"></div>
  </div>
</template>

<script>
import Epub from 'epubjs'
const DOWNLOAD_URL = '/static/2018_Book_AgileProcessesInSoftwareEngine.epub'
global.ePub = Epub
export default {
  methods: {
    // 电子书的解析与渲染
    showEpub() {
      //  生成Book
      this.book = new Epub(DOWNLOAD_URL)
      //  生成Rendition,通过Book.renderTO
      this.rendition = this.book.renderTo('read', {
        width: window.innerWidth,
        height: window.innerHeight
      })
      //  通过Renditon.display渲染电子书
      this.rendition.display()
    }
  },
  mounted() {
    this.showEpub()
  }
}
</script>

<style lang="scss" scoped>
</style>