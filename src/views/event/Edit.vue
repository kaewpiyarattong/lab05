<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit </button>
</template>

<script>
export default {
  props: ['event'],
  inject:['GStore'],
  methods: {
    edit(){
      this.GStore.flashMessage2 = this.event.title + ' already EDIT'
      setTimeout(()=>{
        this.GStore.flashMessage2 = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails',
        params:{id: this.event.id}
      })
    }
  },
}
</script>


