<template>
  <div class="home">
    <Sample
      :firstname="firstname"
      :lastname="lastname"
      :age="age"
      :fruits="fruits"
      @age="changeAge"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import Sample from '@/components/Sample.vue'

export default {
  name: 'Home',
  components: {
    Sample
  },

  data () {
    return {
      firstname: 'Ali',
      lastname: 'Bidkhori',
      age: '15',
      fruits: ['apple', 'orange', 'khiar', 'mooz']
    }
  },

  methods: {
    changeAge (age) {
      this.age = age + 1
    }
  }
}
</script>
