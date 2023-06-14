<template>
  <transition name="popUp-animation">
    <div v-show="popUpActive">
      <div :class="{ 'has-background-white': popUpActive }" class="modal-content box">
        <i @click="close" class="far fa-times-circle has-text-info is-flex is-justify-content-flex-end is-clickable"></i>
        <!--PopUp Content-->
        <slot />
        <button 
          type="button"
          @click="close" 
          class="button is-info is-light is-normal is-hovered is-clickable is-focused is-fullwidth mt-4 is-size-5"
        >
          Close
        </button>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: ["popUpActive"],
  setup(props, { emit }) {
    const close = () => {
      emit("close");
    };

    return { close };
  },
}
</script>

<style scoped>
.popUp-animation-enter-active,
.popUp-animation-leave-active {
  transition: opacity 0.3s cubic-bezier(0.52, 0.02, 0.19, 1.02);
}

.popUp-animation-enter-from,
.popUp-animation-leave-to {
  opacity: 0;
}
</style>