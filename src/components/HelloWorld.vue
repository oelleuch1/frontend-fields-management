<template>
  <h1 v-html="msg"></h1>

  <div :class="boxActive" class="card">
    <button type="button" :disabled="count > 4" v-on:click="incrementCount">count is {{ count }}</button>
    <div> {{ getLabel() }}</div>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <div>{{ fullName }}</div>

  <input placeholder="Name" v-model="count" />

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>

  <ul>
    <li v-for="(element, index) in items" >
       {{ element }}
    </li>
  </ul>

</template>

<script>
export default {
  data() {
    return {
      msg: '<ul> <li> Hello world! </li> <li> Vue Project</li> </ul>',
      count: 0,
      name: 'Emna',
      lastName: 'DOGHMANE',
      items: [
          'Element 1',
          'Element 12',
          'Element 3',
          'Element 55',
      ]
    }
  },
  computed: {
    fullName() {
      return this.name + ' ' + this.lastName
    },
    boxActive() {
      return this.name === 'Emna' ? 'active' : 'inactive'
    }
  },
  methods: {
    incrementCount() {
      this.count++;
      this.name = 'Oussama'
    },
    getInput(event) {
      event.preventDefault()
      console.log(event.target.value)
    },
    getLabel() {
      if (this.count < 3) {
        return 'Under 3'
      } else {
       return 'Greater than 3'
      }
    },
    setCount(event) {
      this.count = event.target.value
    }
  }
}
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
