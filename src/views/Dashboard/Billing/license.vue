<template>
  <billing-layout @selectTariff="selectTariff($event)" />
  <modal-left
      :modalState="modalState"
      @toggleModal="toggleModal($event)"
  >
    <select-plan :currentTariff="currentTariff" />
  </modal-left>
</template>

<script>
import billingLayout from "./billing-layout";
import modalLeft from "./modal-left";
import selectPlan from "../../../components/Dashboard/Billing/select-plan";
import {ref} from "vue";

export default {
  name: 'App',
  components: {
    billingLayout,
    modalLeft,
    selectPlan
  },
  setup() {
    const modalState = ref(false);

    function toggleModal(state) {
      modalState.value = state;
    }

    let currentTariff = ref(null);

    function selectTariff(item) {
      currentTariff.value = item;
      toggleModal(true);
    }

    return { modalState, toggleModal, selectTariff, currentTariff }
  }
}
</script>