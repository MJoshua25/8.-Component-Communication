<template>
  <li>
    <h2>{{ friend.name }} {{ friend.isFavorite ? '(Favorite)' : '' }}</h2>
    <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
    <button @click="toggleFavorite">toggle Favorite</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ friend.phone }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ friend.email }}
      </li>
    </ul>
    <button @click="deleteFriend">Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    friend: {
      type: Object,
      required: true,
    },
  },
  emits: {
    'toggle-favorite': function (id){
       return id ? true : false; 
    },
    'delete-friend': function (id){
       return id ? true : false; 
    }
  },
  data() {
    return {
      detailsAreVisible: false
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.friend.id);
    },
    deleteFriend() {
      this.$emit('delete-friend', this.friend.id);
    }
  }
};
</script>