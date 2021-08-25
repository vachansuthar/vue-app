<template>
   <div>
    <h4>{{title}}</h4>
    {{childB}}
    <button type="button" v-on:click="changeParent">change parent</button>
    <button type="button" v-on:click="changeSibling">change ChildA</button>
  </div>
</template>

<script>

export default {
  name: 'ChildB',
  props: ['title'],
  data() {
    return {
      childB: 'This a ChildB div'
    }
  },
  created() {
    this.$root.$on('changeChildAEmit', (msg)=> {
      this.childB += msg
    })
  },
  methods: {
    changeParent() {
      this.$emit('changeParentEmit', 'changed from ChildB');
    },
    changeSibling() {
      this.$root.$emit('changeChildBEmit', '-changed from ChildB');
    }
  }
}
</script>
