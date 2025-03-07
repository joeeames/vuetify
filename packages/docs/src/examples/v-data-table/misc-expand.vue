<template>
  <v-data-table
    v-model:expanded="expanded"
    :headers="dessertHeaders"
    :items="desserts"
    item-value="name"
    show-expand
  >
    <template v-slot:top>
      <v-toolbar flat>
        <v-toolbar-title>Expandable Table</v-toolbar-title>
      </v-toolbar>
    </template>
    <template v-slot:item.data-table-expand="{ internalItem, isExpanded, toggleExpand }">
      <v-btn
        :icon="isExpanded(internalItem) ? 'mdi-chevron-up' : 'mdi-chevron-down'"
        size="small"
        variant="plain"
        @click="toggleExpand(internalItem)"
      ></v-btn>
    </template>
    <template v-slot:expanded-row="{ columns, item }">
      <tr>
        <td :colspan="columns.length">
          More info about {{ item.name }}
        </td>
      </tr>
    </template>
  </v-data-table>
</template>

<script setup>
  import { ref } from 'vue'

  const expanded = ref([])
  const dessertHeaders = ref([
    {
      title: 'Dessert (100g serving)',
      align: 'start',
      sortable: false,
      key: 'name',
    },
    { title: 'Calories', key: 'calories' },
    { title: 'Fat (g)', key: 'fat' },
    { title: 'Carbs (g)', key: 'carbs' },
    { title: 'Protein (g)', key: 'protein' },
    { title: 'Iron (%)', key: 'iron' },
    { title: '', key: 'data-table-expand' },
  ])
  const desserts = ref([
    {
      name: 'Frozen Yogurt',
      calories: 159,
      fat: 6,
      carbs: 24,
      protein: 4,
      iron: 1,
    },
    {
      name: 'Ice cream sandwich',
      calories: 237,
      fat: 9,
      carbs: 37,
      protein: 4.3,
      iron: 1,
    },
    {
      name: 'Eclair',
      calories: 262,
      fat: 16,
      carbs: 23,
      protein: 6,
      iron: 7,
    },
    {
      name: 'Cupcake',
      calories: 305,
      fat: 3.7,
      carbs: 67,
      protein: 4.3,
      iron: 8,
    },
    {
      name: 'Gingerbread',
      calories: 356,
      fat: 16,
      carbs: 49,
      protein: 3.9,
      iron: 16,
    },
    {
      name: 'Jelly bean',
      calories: 375,
      fat: 0,
      carbs: 94,
      protein: 0,
      iron: 0,
    },
    {
      name: 'Lollipop',
      calories: 392,
      fat: 0.2,
      carbs: 98,
      protein: 0,
      iron: 2,
    },
    {
      name: 'Honeycomb',
      calories: 408,
      fat: 3.2,
      carbs: 87,
      protein: 6.5,
      iron: 45,
    },
    {
      name: 'Donut',
      calories: 452,
      fat: 25,
      carbs: 51,
      protein: 4.9,
      iron: 22,
    },
    {
      name: 'KitKat',
      calories: 518,
      fat: 26,
      carbs: 65,
      protein: 7,
      iron: 6,
    },
  ])
</script>

<script>
  export default {
    data () {
      return {
        expanded: [],
        dessertHeaders: [
          {
            title: 'Dessert (100g serving)',
            align: 'start',
            sortable: false,
            key: 'name',
          },
          { title: 'Calories', key: 'calories' },
          { title: 'Fat (g)', key: 'fat' },
          { title: 'Carbs (g)', key: 'carbs' },
          { title: 'Protein (g)', key: 'protein' },
          { title: 'Iron (%)', key: 'iron' },
          { title: '', key: 'data-table-expand' },
        ],
        desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: 1,
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: 1,
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: 7,
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: 8,
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: 16,
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: 0,
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: 2,
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: 45,
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: 22,
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: 6,
          },
        ],
      }
    },
  }
</script>
