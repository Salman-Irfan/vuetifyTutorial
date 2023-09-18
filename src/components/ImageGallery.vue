<script setup>
import {defineProps} from "vue";
const p = defineProps(["isWithColor"])
</script>
<template>
    <VCard class="mx-5 my-2 pa-3">
        <VRow>
            <VCol v-for="n in 200" :key="n" cols="4" sm="3" md="2" lg="1">
                <VCard>
                    <!-- img -->
                    <vImg
                        :src="`https://picsum.photos/500/300?image=${
                            n * 5 + 10
                        }${p.isWithColor ? '' : '&grayscale' }`"
                        :lazy-src="`https://picsum.photos/10/6?image=${
                            n * 5 + 10
                        }${p.isWithColor ? '' : '&grayscale' }`"
                        aspect-ratio="1"
                        cover
                        class="bg-grey-lighten-2"
                    />
                    <!-- template for handling blank image rendering -->
                    <template v-slot:placeholder>
                        <VRow
                            class="fill-height ma-0"
                            align="center"
                            justify="center"
                        >
                            <!-- progressive loading state -->
                            <VProgressCircular
                                indeterminate
                                color="grey-lighten-5"
                            ></VProgressCircular>
                        </VRow>
                    </template>
                </VCard>
            </VCol>
        </VRow>
    </VCard>
</template>
