## vue-wang-editor

A Vue component of [WangEditor](http://www.wangeditor.com/), based on 3.x.

### Install

you can install with npm:

```sh
npm install --save vue-wang-editor
```

or yarn:

```sh
yarn add vue-wang-editor
```

It will install `wangeditor` automatically.

### Usage

You can bind the html string with `v-model`, and `menus` with menu config.

```vue
<template>
<wang-editor
  v-model="detail.context"
  :menus="menus">
</wang-editor>
</template>

<script>
import WangEditor from 'vue-wang-editor'

export default {
  components: { WangEditor }
}

</script>
```

`menus` default value:

```javascript
['head', 'bold', 'italic', 'underline', 'strikeThrough', 'foreColor', 'backColor', 'link', 'list', 'justify', 'quote', 'emoticon', 'image', 'table', 'video', 'code', 'undo', 'redo']
```

You can get [full menu config in [WangEditor Documents])(https://www.kancloud.cn/wangfupeng/wangeditor3/335777).
