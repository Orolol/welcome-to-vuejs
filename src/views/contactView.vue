<template>
  <div>
      <contact-list :list="list"></contact-list>
  </div>
</template>

<script>
import contactList from '../components/contactList'
import jsonList from '../../static/vueworkshop.json';

export default {
  name: 'contactView',
  components: {
    contactList
  },
  data () {
    return {
      list: jsonList
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
