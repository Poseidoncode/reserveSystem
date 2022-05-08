<template>
  <div class="open-icon" v-show="!cartOpen" @click="cartOpen = !cartOpen">
    <i class="pi pi-angle-left" style="font-size: 2rem"></i>
  </div>
</template>

<script>
import { defineComponent, inject, ref, onMounted, watch, computed } from "vue";
import { useToast } from "vue-toastification";
import { citiesData, zonesData } from "@/utils/constant.js";
import { getMapLists } from "Service/apis.js";
import { useStore } from "vuex";
export default defineComponent({
  props: {},
  emits: ["setMarker", "setCenterData"],
  setup(props, { emit }) {
    const store = useStore();
    const cartOpen = ref(true);

    return {};
  },
});
</script>

<style lang="scss" scoped>
.list-content {
  width: 1200px;
}

.open-icon,
.close-icon {
  position: fixed;
  z-index: 1500;
  right: 41px;
  top: 8px;
  cursor: pointer;
  color: #fff;
  background: #1c54d4;
  border-radius: 50%;
  display: flex;
  justify-content: center;
}

.totop-icon {
  position: fixed;
  z-index: 1500;
  right: 41px;

  cursor: pointer;
  color: #fff;
  background: #f5c664;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  bottom: 30px;
}

.p-inputgroup-addon {
  color: #fff;
  background: #1c54d4;
  width: 97px;
}

.hide-item {
  display: block;
}
@media screen and (max-width: 500px) {
  .hide-item {
    display: none !important;
  }
  .open-icon,
  .close-icon {
    top: 29px !important;
  }
}
</style>
