<template>
  <section class="section">
    <div class="container">
      <h1 class="title"> {{ greetingText }} </h1>
      <h1 class="title" v-for="name in names" :key="name">{{ name }}</h1>
      <b-field type="is-info">
          <b-input v-model="name" :placeholder="placeholderTxt"></b-input>
      </b-field>

      <b-button  type="is-info" @click="enter">Enter</b-button>
    </div>
  </section>
</template>

<script>

export default {
  data () {
    return {
      placeholderTxt: "Tell us your name",
      name: null,
      greetingText: "Hello! What's your name?",
    }
  },
  methods: {
    enter () {
      if (!this.name) return
      this.greetingText = "Hello, " + this.name + "!"
      this.name = null
    }
  },
  watch: {
    
  }
}
</script>
