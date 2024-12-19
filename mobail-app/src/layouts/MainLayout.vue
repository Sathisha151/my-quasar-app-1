<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />

        <q-toolbar-title> Barber Shop </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> barber shop navigation </q-item-label>

        <EssentialLink v-for="link in linksList" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Home',
    caption: '',
    icon: 'home',
    link: '',
  },
  {
    title: 'Service list',
    caption: 'Over service list',
    icon: 'service_toolbox',
    link: '',
  },
  {
    title: 'Appointment booking',
    caption: 'You Can appointment booking',
    icon: ' book_online',
    link: '',
  },
  {
    title: 'About us',
    caption: 'You can know about us',
    icon: 'person',
    link: '',
  },
  {
    title: 'Connect us',
    caption: 'connect us you can',
    icon: 'phone_in_talk',
    link: '',
  },
  {
    title: 'Customer reviews',
    caption: 'You have any suggestion',
    icon: 'reviews',
    link: '',
  },
  {
    title: 'Gallery of haircuts',
    caption: 'hear gallery of haircuts',
    icon: 'gallery',
    link: '',
  },
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
