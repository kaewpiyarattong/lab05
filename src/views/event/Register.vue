<template>
  <p>Regstration form here</p>
  <button @click="register">Register Me </button>
</template>

<script>
export default {
  props: ['event'],
  inject:['GStore'],
  methods: {
    register(){
      this.GStore.flashMessage = 'You are Successfully registered for '+ this.event.title
      setTimeout(()=>{
        this.GStore.flashMessage = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails',
        params:{id: this.event.id}
      })
    }
  },
}
</script>
