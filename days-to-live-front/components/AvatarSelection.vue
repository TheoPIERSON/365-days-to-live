<template>
  <section class="flex justify-around bg-emerald-100/50 p-4">
    <!-- Grille des avatars -->
    <div class="grid grid-cols-2 w-1/3 p-2 m-4 border-4 border-emerald-200">
      <NuxtImg
        v-for="(avatar, index) in avatars"
        :key="index"
        class="w-full p-2 rounded-full cursor-pointer hover:scale-105 transition-transform"
        :src="avatar"
        alt="Avatar"
        @click="selectAvatar(avatar)"
      />
    </div>

    <!-- Avatar sélectionné -->
    <div class="w-1/3 m-4 border-4 border-emerald-200 flex justify-center items-center">
      <NuxtImg :src="selectedAvatar" class="w-full rounded-full" alt="Selected Avatar" />
    </div>
  </section>
  <h2>You can pick your avatar</h2>
</template>

<script setup lang="ts">
import { ref } from "vue";

// Liste des avatars disponibles
const avatars = ["/cyberpunk-avatar.webp", "/cowboy-avatar.webp", "/cyberpunk-avatar.webp", "/cyberpunk-avatar.webp"];

// Avatar sélectionné (par défaut, le premier de la liste)
const selectedAvatar = ref(avatars[0]);

// Fonction pour sélectionner un avatar
const selectAvatar = (avatar: string) => {
  selectedAvatar.value = avatar;
};
</script>
