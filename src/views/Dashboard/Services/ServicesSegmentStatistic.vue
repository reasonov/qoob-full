<template>
  <div>
    <h5 class="mt-3 mb-4 fw-600">{{ content.title }}</h5>
    <cm-card :ratio="43.0379746">
      <img src="@/assets/services-segments.jpg" style="width: 100%; height: auto;">

    </cm-card>
  </div>
</template>

<script>
import {mapState} from "vuex";
import CmCard from "@/components/UI/CmCard";

export default {
name: "ServicesSegmentStatistic",
  components: {CmCard},
  computed: {
    ...mapState({
      content: state => state.texts.dashboard.services.segmentStatistic,
    }),
  }
}
</script>

<style scoped>

</style>