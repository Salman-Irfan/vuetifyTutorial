<script setup>
import { defineEmits } from 'vue';
const emits = defineEmits(['selectOption']);
const selectOption = (isColor) => {
    emits("selectOption", isColor);
}
</script>

<template>
    <VNavigationDrawer expand-on-hover rail>
        <VListItem
            prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
            title="John Leider"
            subtitle="JohnLeider@email.com"
            nav
        >
            <template v-slot:append>
                <VBtn variant="text" icon="mdi-chevron-left" @click.stop></VBtn>
            </template>
        </VListItem>
        <!-- divider -->
        <v-divider></v-divider>

        <v-list density="compact" nav>
            <!-- home -->
            <v-list-item
                prepend-icon="mdi-home-city"
                title="Home"
                value="home"
            ></v-list-item>
            <!-- account -->
            <v-list-item
                prepend-icon="mdi-account"
                title="My Account"
                value="account"
            ></v-list-item>
            <!-- users -->
            <v-list-item
                prepend-icon="mdi-account-group-outline"
                title="Users"
                value="users"
            ></v-list-item>
            <!-- my files -->
            <v-list-item
                prepend-icon="mdi-folder"
                title="Folder"
                value="Folder"
            ></v-list-item>
            <!-- stars -->
            <v-list-item
                prepend-icon="mdi-star"
                title="Star"
                value="Star"
            ></v-list-item>
            <!-- color gallery -->
            <v-list-item
                prepend-icon="mdi-image"
                title="Color gallery"
                value="color"
                @click="selectOption(true)"
            ></v-list-item>
            <!-- dialpad -->
            <v-list-item
                prepend-icon="mdi-dialpad"
                title="Greyspace gallery"
                value="image"
                @click="selectOption(false)"
            ></v-list-item>
        </v-list>
    </VNavigationDrawer>
</template>
