<template>
  <q-markup-table flat bordered>
      <thead class="bg-teal">
        <tr>
          <th colspan="8">
            <div class="row no-wrap items-center ">
              <q-img
                style="width: 70px"
                :ratio="1"
                class="rounded-borders"
                src="./../../../src/assets/images.jpg"
              />

              <div class="text-h4 q-ml-md text-white">Employees</div>
              <q-space />
              <div>
                <q-btn color="white" class="q-ma-md" text-color="black" label="Select All"  @click="selectAll"></q-btn>
                <q-btn color="white" class="q-ma-md" text-color="black" label="Unselect All"  @click="unselectAll"></q-btn></div>
            </div>
          </th>
        </tr>
        <tr>
          <th class="text-left">Select</th>
          <th class="text-left">Id</th>
          <th class="text-left">Name</th>
          <th class="text-center">Age</th>
          <th class="text-right">Salary</th>
          <th class="text-right">Photo</th>
        </tr>
      </thead>
      <tbody class="bg-grey-3" clickable v-ripple>
        <tr v-for="(employee, index) in employeesList" :key="index">
         <q-checkbox
           v-model="employee.selectEmployees"
           @click="updateEmployee"
           color="teal" />
          <td class="text-left">{{ employee.id }}</td>
          <td class="text-left">{{ employee.employee_name }}</td>
          <td class="text-center">{{ employee.employee_age }}</td>
          <td class="text-right">{{ employee.employee_salary }}</td>
          <td class="text-right">{{ employee.profile_image }}</td>
        </tr>
      </tbody>
    </q-markup-table>
</template>

<script>
  import { mapActions } from 'vuex'

  export default{
    props:{
      employeesList: {
        require: true,
        type: Array,
        selectEmployees: []
      }
    },
    methods: {
      ...mapActions('employees', ['updateEmployee']),

    }
  }
</script>
