<template>
  <div class="conta">
    <modalCards-component :card="newCard" />
    <b-button variant="success" @click="createCard()" block>Create</b-button>
  </div>
</template>

<script>
export default {
  name: "create-component",
  data() {
    return {
      newCard: {
        id: new Date().getTime(),
        title: "New Card",
        body: "This is the new card body",
        flag: true,
      },
    };
  },
  methods: {
    createCard() {
      this.$root.$emit("bv::show::modal", this.newCard.id.toString());
    }
  }
};
</script>
