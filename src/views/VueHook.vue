<template>
  <div class="about">
    <h1>This is an vue life cycle hook page</h1>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
export default {
  name: 'VueHook',
  props: {
    msg: String
  },
  data() {
    return {
      name: 'Basant'
    }
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  created() {
    console.log('created');
  },
  beforeMount() {
    // this.name='Basant Suthar'
    console.log('beforeMount', this.$el);
  },
  mounted() {
    console.log('mounted', this.$el);
  },
  beforeUpdate() {
    console.log('beforeUpdate');
  },
  updated() {
    console.log('updated');
  },
  beforeDestroy() {
    console.log('beforeDestroy');
  },
  destroyed() {
    console.log('destroyed');
  }
}
</script>