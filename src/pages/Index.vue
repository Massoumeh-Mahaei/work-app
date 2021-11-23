<template>
  <q-page padding>
    <Employee-component
      :employeesList='getEmployee'/>
  </q-page>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters('employeesStore', ['getEmployee'])
  },
  components: {  
      'Employee-component': require('components/Employees/Employee.vue').default
  }
}
</script>
