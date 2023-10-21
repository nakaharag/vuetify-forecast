<script setup>

</script>

<template>
  <transition :css="false">
    <v-container>
    <v-row>
      <v-col cols="12" sm="6" md="3">
        <v-card>
          <v-card-title>
            <span class="headline">Card Title</span>
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Culpa deserunt dicta dignissimos doloremque
            dolores doloribus, ducimus eius error esse et eveniet ex excepturi fugiat harum impedit in incidunt
            inventore ipsa.
          </v-card-text>

          <v-autocomplete
            label="Type a city.."
            :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
          ></v-autocomplete>

          <v-card-actions>
            <v-btn color="primary">Share</v-btn>
            <v-btn color="primary">Explore</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
  </transition>

</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
