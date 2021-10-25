<template>
  <div class="logo">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1>
      {{ "Fullname : " + fullname }}
    </h1>
    <p>
      {{ "Age : " + age }}
    </p>
    <p v-if="age > 16">
      {{ firstname + " is older than 16 " }}
    </p>
    <p v-else>
      {{ firstname + " is younger than 16 " }}
    </p>
    <strong> My favorite fruits : </strong>
    <ul>
      <li v-for="(fruit, index) in fruits" :key="index">
        {{ fruit }}
      </li>
    </ul>
    <button @click="changeAge(age)">click me</button>
  </div>
</template>

<script>
export default {
  name: 'sample',
  props: {
    firstname: {
      type: String,
      default: ''
    },
    lastname: {
      type: String,
      default: ''
    },
    age: {
      type: Number,
      default: 0
    },
    fruits: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    fullname () {
      const output = this.firstname + ' ' + this.lastname
      return output
    }
  },
  methods: {
    changeAge (age) {
      this.$emit('age', age)
    }
  }
}
</script>
