<script>

// 声明式渲染，可以提高开发效率 vue2 语法
export default {
  data() {
    return {
      age: 17,
      sex:"woman"
    }
  },
  methods: {
  },
  watch: { 
  },
}

</script>

<template>
    <div>
      <!-- v-if 指令用于条件性地渲染一块内容。这块内容只会在指令的表达式返回真值时才被渲染。 -->
      <!-- 一个 v-else 元素必须跟在一个 v-if 或者 v-else-if 元素后面，否则它将不会被识别。 -->

      <p v-if="age > 18">我是成年人</p>
      <p v-else-if="age == 18">我现在处于中间点</p>
      <p v-if="age < 18">我不是成年人</p>
    </div>
    <!-- 在 template 元素上使用 v-if 条件渲染分组 -->
    <template v-if="age>=18">
        <p>18🈲</p>
        <p>18🈲</p>
        <p>18🈲</p>
        <p>18🈲</p>
    </template>
    <br/>

    <!-- 不同之处在于 v-show 会在 DOM 渲染中保留该元素；v-show 仅切换了该元素上名为 display 的 CSS 属性。
    v-show 不支持在 <template> 元素上使用，也不能和 v-else 搭配使用。 -->
    <p v-show="sex == 'woman'">男生</p>

    <!-- v-if vs. v-show#
    v-if 是“真实的”按条件渲染，因为它确保了在切换时，条件区块内的事件监听器和子组件都会被销毁与重建。
    v-if 也是惰性的：如果在初次渲染时条件值为 false，则不会做任何事。条件区块只有当条件首次变为 true 时才被渲染。
    相比之下，v-show 简单许多，元素无论初始条件如何，始终会被渲染，只有 CSS display 属性会被切换。
    总的来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。
    因此，如果需要频繁切换，则使用 v-show 较好；如果在运行时绑定条件很少改变，则 v-if 会更合适。 -->

</template>

<style scoped>

</style>
