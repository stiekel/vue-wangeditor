<template>
<div id="vue-wangeditor" ref="editor"></div>
</template>

<script type="text/javascript">
import WangEditor from 'wangeditor'

// default WangEditor menu config
const DEFAULT_MENUS = ['head', 'bold', 'italic', 'underline', 'strikeThrough', 'foreColor', 'backColor', 'link', 'list', 'justify', 'quote', 'emoticon', 'image', 'table', 'video', 'code', 'undo', 'redo']

export default {
  name: 'VueWangEditor',
  // @props {string} content html string
  // @props {object} menus
  props: ['value', 'menus'],
  data () {
    return {
      // instance of wangEditor
      instance: null
    }
  },
  methods: {
    // init dom and WangEditor instance
    init () {
      this.$set(this, 'instance', new WangEditor(this.$refs.editor))
      this.instance.customConfig.menus = this.weMenus
      this.instance.customConfig.onchange = (html) => {
        this.$nextTick(_ => {
          this.$emit('input', html)
        })
      }
      this.instance.create()
      this.instance.txt.html(this.value)
    }
  },
  computed: {
    weMenus () {
      if (this.menus && this.menus instanceof Array && this.menus.length) {
        return this.menus
      } else {
        return DEFAULT_MENUS
      }
    }
  },
  mounted () {
    this.init()
  }
}
</script>
