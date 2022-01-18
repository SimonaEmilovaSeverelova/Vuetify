<template>
  <div>
    <v-container>
      <v-row justify="center">
        <EmployeeCard
          v-for="empl of employees"
          :key="empl.id"
          :employee="empl"
        />
      </v-row>
    </v-container>
  </div>
</template>

<script>
import EmployeeCard from "@/components/EmployeeCard";

export default {
  components: {
    EmployeeCard,
  },
  props: {
    employees: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>