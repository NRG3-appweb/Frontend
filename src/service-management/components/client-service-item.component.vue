<script>
import {Service} from "../model/service.entity.js";

export default {
  name: "service-item",
  props: {
    service: {
      type: Service,
      required: true
    }
  },
  methods: {
    redirectToServiceDetail(serviceId) {
      this.$router.push({ name: 'Service', params: { id: serviceId } });
    }
  }
}
</script>

<template>
  <pv-card style="width: 20rem; height: auto;overflow: hidden">
    <template #header>
      <img alt="user header" :src="service.img" width="320px"/>
    </template>
    <template #title> {{ service.service_name }}</template>
    <template #subtitle>Price: {{ service.price }}</template>
    <template #content>
      <p class="m-0">
        {{ service.description }}
      </p>
    </template>
    <template #footer>
      <div class="flex gap-4 mt-1">
        <pv-button icon="pi pi-arrow-right"
                   icon-pos="right"
                   label="Learn More"
                   class="w-full"
                   @click="redirectToServiceDetail(service.id)"/>
      </div>
    </template>
  </pv-card>
</template>

<style scoped>

</style>