<template>
  <div>
    <h3>v-text</h3>
    <div v-text="firstName"></div>
    <hr/>

    <h3>v-html</h3>
    <div v-html="boldText"></div>
    <hr/>

    <h3>v-bind</h3>
    <div v-bind:id="'test_id'" v-bind:class="[1==0 ? 'true' : 'false']">v-bind demo</div>
    <hr/>

    <h3>v-model</h3>
    <input type="text" v-model="firstName" />
    <hr/>

    <h3>v-show / v-if / v-esle</h3>
    <br/>
    <input type="checkbox" v-model="isChecked" /> Is show
    <br/><br/>
    <div v-show="isChecked">This is show/hide div</div>
    <br/>
    <div v-if="isChecked">This is if div</div>
    <div v-else>This is else div</div>
    <hr/>

    <h3>v-for</h3>
    <ul>
      <li v-for="(fruit,index) in fruits" v-bind:key="index">
        {{fruit}}
      </li>
    </ul>
    <hr/>

    <h3>v-on (event binding)</h3>
    <button type=button v-on:click="changeFirstName">change name</button>
    <hr/>

    <h3>computed property</h3>
    {{fullName}}
    <hr/>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  data() {
    return {
      firstName: 'Basant',
      lastName: 'Suthar',
      boldText: '<b>This is bold text</b>',
      isChecked: true,
      fruits: ['Mango', 'Banana', 'Apple']
    }
  },
  computed: {
    fullName() {
      return this.firstName+' '+this.lastName
    }
  },
  methods: {
    changeFirstName() {
      this.firstName = 'Basant Suthar'
    },
    anotherMethod() {}
  },
  watch: {
    firstName(newVal, oldVal) {
      console.log(newVal);
      console.log(oldVal);
    },
    lastName(n,o) {
      
    }
  }
}
</script>