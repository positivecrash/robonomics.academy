<template>
    <div class="popup__overlay" @click="$store.commit('HIDE_IMAGE_POPUP')">
      <div class="popup__content">
        <g-image :src="picture"></g-image>
      </div>
    </div>
</template>

<script>
export default {

  computed: {
    picture() {
      return require(`!!assets-loader!@imagesCourses/${this.$store.state.imagePopupSrc}`)
    }
  }

}
</script>

<style scoped>


.popup__content {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: var(--gap);
  width: 80%;
  height: 90%;
  /* background-color: var(--color-light);
  border: 2px solid var(--color-brown); */
  border-radius: 20px;
  transform: scale(0.3);
  overflow: auto;
}

.popup__content img {
  height: 100%;
  object-fit: contain;
  width: 100%;
}


@media screen and (max-width: 980px) {
  .popup__content {
    width: 92%;
  }
}


@media screen and (max-width: 650px) {
  .popup__content {
    width: 100%;
  }
}

</style>