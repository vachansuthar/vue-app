<template>
  <div>
    <input type="text" v-model="parent" />
    <button type="button" v-on:click="changeTitle">change title</button>
    <br/><br/>
    <ChildA v-bind:title="title" v-bind:title1="title" @changeParentEmit="changeParent" />
    <br/>
    <ChildB v-bind:title="title" @changeParentEmit="changeParent" />
  </div>
</template>

<script>
// @ is an alias to /src
import ChildA from '@/views/ChildA.vue'
import ChildB from '@/views/ChildB.vue'

export default {
  name: 'Parent',
  components: {
    ChildA,
    ChildB
  },
  data() {
    return {
      parent: 'This a parent div',
      title: 'child component chaned'
    }
  },
  methods: {
    changeTitle() {
      this.title += '-changed'     
    },
    changeParent(msg) {
      this.parent = msg;
    }
  }
}
</script>
