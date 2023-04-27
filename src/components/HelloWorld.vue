<script lang="ts">
import { defineComponent } from 'vue'
import type { PropType } from 'vue'

type Book = {
  id: string,
  name: string
}

export default defineComponent({
  props: {
    msg: String,
    book: {
      type: Object as PropType<Book>,
      required:true
    },
    callback:Function as PropType<()=>void>
  },
  data() { 
    return {
      count: 0 as number,
      name: '' as string,
      age:10 as number
    }
  },
  methods: {
    changeName(name:string) { 
      this.name = name
    },
    changeNumber(age: number) { 
      this.age = age 
    }
  }
})


</script>

<template>
  <h1>{{ msg }}</h1>

  <input type="text" v-model="age">
  <h2>{{ age }}</h2>

  <input type="text" v-model="name">
  <h2>{{ name }}</h2>
  
  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

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
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
