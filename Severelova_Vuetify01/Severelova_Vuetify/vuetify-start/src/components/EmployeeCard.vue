<template>
  <v-card class="mx-8 my-6" width="18rem">
    <v-img
      :src="employee.picture.large | path"
      max-width="200"
      class="white--text mx-auto"
      alt="picture of employee"
      align="center"
    >
      <v-card-title class="align-end fill-height empl-name"
        >{{ employee.name.title }} {{ employee.name.first }}
        {{ employee.name.last }}</v-card-title
      >
    </v-img>
    <v-card-text>
      <span class="text--primary">
        <span>Email: {{ employee.email }}</span>
        <br />
        <span>Phone: {{ employee.phone }}</span>
      </span>
    </v-card-text>
    <v-card-actions>
      <v-btn text outlined @click="$emit('delete', employee)"
        ><span>Delete </span><v-icon>mdi-delete</v-icon></v-btn
      >
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    employee: Object,
  },
  filters: {
    path: function (filename) {
      return "http://localhost:3000/" + filename;
    },
  },
};
</script>

<style lang="scss" scoped>
.empl-name {
  text-shadow: 3px 3px black;
}
</style>