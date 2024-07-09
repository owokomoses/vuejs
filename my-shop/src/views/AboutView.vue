<script setup>
import { ref } from 'vue';

const variants = ref(['outlined', 'elevated', 'flat']); // Example variants
</script>

<template>
  <v-card class="mx-auto mt-10" max-width="full" style="margin-top: -64px;">
    <v-toolbar flat>
      <v-toolbar-title class="text-black">
        Title
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon style="color: black;">mdi-apps</v-icon>
      </v-btn>
    </v-toolbar>

    <v-divider></v-divider>

    <v-card-text style="height: 200px;">
      <v-row dense>
        <v-col
          v-for="(variant, i) in variants"
          :key="i"
          cols="12"
          md="4"
        >
          <v-card
            :variant="variant"
            class="mx-auto"
            color="surface-variant"
            max-width="344"
            subtitle="Greyhound divisely hello coldly fonwderfully"
            title="Headline"
          >
            <template v-slot:actions>
              <v-btn text>Button</v-btn>
            </template>
          </v-card>

          <div class="text-center text-caption">{{ variant }}</div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<style>
</style>
