<template>
  <div>
    <h5 class="mt-3 mb-4 fw-600">{{ content.title }}</h5>
    <cm-card :ratio="43.0379746">
      <div class="position-relative h-100">
        <img src="@/assets/mainIndicators.jpg" style="width: 100%; height: auto">
        <div class="btnFlow d-flex">
          <cm-button
            @click="$router.push({'name': 'notificationSegments'})"
          >Подробнее</cm-button>
        </div>
      </div>
    </cm-card>
  </div>
</template>

<script>
import {mapState} from "vuex";
import CmCard from "@/components/UI/CmCard";
import CmButton from "@/components/UI/buttons/CmButton";

export default {
name: "ServicesClientFlow",
  components: {CmButton, CmCard},
  computed: {
    ...mapState({
      content: state => state.texts.dashboard.services.clientFlow,
    }),
  }
}
</script>

<style scoped>
.btnFlow{
  position: absolute;
  left: 0;
  bottom: 0;
}
</style>