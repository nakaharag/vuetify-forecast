<template>
  <v-navigation-drawer
        expand-on-hover
        rail=rail
        border=false
        class="bg-indigo-lighten-5"
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            title="Gustavo Nakahara"
            subtitle="github.com/nakaharag"
            class="bg-shades-transparent"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-folder" title="My Files" value="myfiles"></v-list-item>
          <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
          <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>
</template>
<script>
  import {ref} from "vue";
  const rail = ref<Boolean>true
</script>
