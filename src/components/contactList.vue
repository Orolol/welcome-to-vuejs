<template>
  <div>
    <input type="text" v-model="filter"/>
    <contact v-for="contact in list" :contact="contact" :key="contact.id"></contact>
  </div>
</template>

<script>
import contact from './contact'
export default {
  name: 'contactList',
  components: {
    contact
  },
  props: ['list'],
  computed: {
    sortedAndFilteredList(){
      return this.list
    }
  },
  data(){
    return {
      sort: null,
      filter: null
    }
  },
  methods: {
    sortContacts(){
      //TODO
    },
    filterContacts(){
      //TODO
    }
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
