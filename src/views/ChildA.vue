<template>
  <div>
    <h4>{{title1}}</h4>
    {{childA}}
    <button type="button" v-on:click="changeParent">change parent</button>
    <button type="button" v-on:click="changeSibling">change ChildB</button>
  </div>
</template>

<script>

export default {
  name: 'ChildA',
  props: ['title', 'title1'],
  data() {
    return {
      childA: 'This a ChildA div'
    }
  },
  created() {
    this.$root.$on('changeChildBEmit', (msg)=> {
      this.childA += msg
    })
  },
  methods: {
    changeParent() {
      this.$emit('changeParentEmit', '-changed from ChildA');
    },
    changeSibling() {
      this.$root.$emit('changeChildAEmit', '-changed from ChildA');
    }
  },
}
</script>

<style scoped>

</style>