<template>
  <q-layout view="lHh Lpr lFf">
    <q-header unelevated>
      <q-toolbar class="bg-grey">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Zona Laundry DO-JO
        </q-toolbar-title>

        <div></div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Bersih sekejap
        </q-item-label>
        <q-item clickable active-class="active" exact v-ripple :to="{ name: 'dashboard'}">
          <q-item-section avatar>
            <q-icon name="list" />
          </q-item-section>

          <q-item-section>
            List Laundry
          </q-item-section>
        </q-item>
        <q-item clickable active-class="active" exact v-ripple :to="{ name: 'inputLaundry'}">
          <q-item-section avatar>
            <q-icon name="input" />
          </q-item-section>

          <q-item-section>
            Input Laundry
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container class="bg-grey-3">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data () {
    return {
      leftDrawerOpen: false
    }
  }
}
</script>
