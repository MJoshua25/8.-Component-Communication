<template>
  <form>
      <div>
          <label>Name</label>
          <input v-model="friend.name" type="text"/>
      </div>
      <div>
          <label>Phone</label>
          <input v-model="friend.phone" type="text"/>
      </div>
      <div>
          <label>E-Mail</label>
          <input v-model="friend.email" type="email"/>
      </div>
      <div>
          <button>Add contact</button>
      </div>
  </form>
</template>

<script>
export default {
    props: {

    },
    data () {
        return {
            friend: {
                name: "",
                phone: "",
                email: "",
            }
        }
    },
    methods: {

    }
}
</script>

<style>

</style>