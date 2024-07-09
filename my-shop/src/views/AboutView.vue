<script setup>
import { ref } from 'vue';

const items = ref([
  { id: 1, name: 'Item 1', description: 'Description for Item 1', quantity: 0 },
  { id: 2, name: 'Item 2', description: 'Description for Item 2', quantity: 0 },
  { id: 3, name: 'Item 3', description: 'Description for Item 3', quantity: 0 },
  { id: 4, name: 'Item 4', description: 'Description for Item 4', quantity: 0 },
  { id: 5, name: 'Item 5', description: 'Description for Item 5', quantity: 0 },
  { id: 6, name: 'Item 6', description: 'Description for Item 6', quantity: 0 },
]);

const cart = ref([]);

function addToCart(item) {
  const cartItem = cart.value.find(cartItem => cartItem.id === item.id);
  if (cartItem) {
    cartItem.quantity++;
  } else {
    cart.value.push({ ...item, quantity: 1 });
  }
}

function removeFromCart(item) {
  const cartItem = cart.value.find(cartItem => cartItem.id === item.id);
  if (cartItem) {
    if (cartItem.quantity > 1) {
      cartItem.quantity--;
    } else {
      cart.value = cart.value.filter(cartItem => cartItem.id !== item.id);
    }
  }
}

function buyItems() {
  console.log('Buying items:', cart.value);
  // Implement the buying logic here
}

function removeAllItems() {
  cart.value = [];
}
</script>

<template>
  <v-card class="mx-auto mt-10" max-width="full" style="margin-top: -64px;">
    <v-toolbar flat>
      <v-toolbar-title class="text-black">
        Products
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon style="color: black;">mdi-apps</v-icon>
      </v-btn>
    </v-toolbar>

    <v-divider></v-divider>

    <v-card-text style="height: 500px;">
      <v-row dense>
        <v-col
          v-for="item in items"
          :key="item.id"
          cols="12"
          md="4"
        >
          <v-card
            class="mx-auto"
            color="surface-variant"
            max-width="350"
          >
            <v-card-title>{{ item.name }}</v-card-title>
            <v-card-subtitle>{{ item.description }}</v-card-subtitle>
            <v-card-actions>
              <v-btn text @click="addToCart(item)">Add to Cart</v-btn>
              <v-btn text @click="removeFromCart(item)">Remove from Cart</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>

      <v-divider class="my-4"></v-divider>

      <h3 class="text-h6">Cart</h3>
      <v-row dense>
        <v-col
          v-for="cartItem in cart"
          :key="cartItem.id"
          cols="12"
          md="4"
        >
          <v-card
            class="mx-auto"
            color="surface-variant"
            max-width="350"
          >
            <v-card-title>{{ cartItem.name }} ({{ cartItem.quantity }})</v-card-title>
            <v-card-actions>
              <v-btn text @click="removeFromCart(cartItem)">Remove One</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>

      <v-row class="mt-4">
        <v-col cols="12" class="text-center">
          <v-btn @click="buyItems">Buy</v-btn>
          <v-btn @click="removeAllItems">Remove All</v-btn>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<style>
</style>
