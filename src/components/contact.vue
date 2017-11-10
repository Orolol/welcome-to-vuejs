<template>
  <div>

    <div><img :src="contact.pic" /></div><span @click="deleteContact">X</span>
    <div>
      <select v-model="contact.gender">
        <option value="Male">M</option>
        <option value="Female">Mme</option>
      </select>
      <input v-model="contact.first_name" type="text" />
      <input v-model="contact.last_name" type="text" />
    </div>
    <div><input v-model="contact.job_title" type="text" /> since <input v-model="contact.employed_since" type="text" /></div>
    <div><input v-model="contact.email" type="text" /></div>
    <!-- <div> TODO PHONEs </div> -->
    
  </div>
</template>

<script>
export default {
  name: 'contact',
  props: ['contact' ],
  watch: {
    contact: {
      handler: function (val, oldVal) { 
        console.log("change ", val)
      },
      deep: true
    }
  },
  methods: {
    deleteContact(){
       console.log("delete ", this.contact.id)
       //TODO
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
