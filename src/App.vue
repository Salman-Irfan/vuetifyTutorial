<script setup>
// import sidebar
import ImageGallery from "./components/ImageGallery.vue";
import SideBar from "./components/SideBar.vue";
// ref
import { ref } from "vue";
// utlizing ref
const isWithColor = ref(true);
const onSelectOption = (isColor) => {
    isWithColor.value = isColor;
};
</script>
<!-- template -->
<template>
    <VApp class="rounded rounded-md">
        <!-- sidebar -->
        <SideBar @selectOption="onSelectOption" />
        <VMain
            class="d-flex align-center justify-center"
            style="min-height: 300px"
        >
            <!-- cards -->
            <ImageGallery :isWithColor="isWithColor" />
        </VMain>
    </VApp>
</template>

<script>
export default {
    name: "App",
    data: () => ({
        //
    }),
};
</script>
