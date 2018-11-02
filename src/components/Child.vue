<template>
  <div @click="select" :class="state" class="option">
    {{name}}
  </div>
</template>

<script>
export default {
  name: 'Child',
  data () {
    return {
    }
  },
  computed: {
    state () {
      return this.name === this.selected ? 'active' : 'inactive'
    }
  },
  methods: {
    select () {
      this.$emit('change', this.name)
    }
  },
  props: ['name', 'selected']
}
</script>

<style scoped>
.option {
  padding: 1rem;
}
.active {
  background-color: red;
  color: white;
}
</style>
