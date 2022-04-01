<template>
  <div class="crud_holder">
    <div class="crud_form">
      <div class="inner_crud_form">
        Please enter the data

        <input v-model="emp.name" type="text" placeholder="Name" />
        <input v-model="emp.phone" type="text" placeholder="Phone Number" />
        <input v-model="emp.department" type="text" placeholder="Department" />
        <input v-model="emp.code" type="text" placeholder="Emp Code" />
        <button @click="submitData">Submit</button>
      </div>
    </div>
    <div class="data_list">
      <div class="data_list_inner">
        <table>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Phone Number</th>
            <th>Department</th>
            <th>Emp Code</th>
            <th>Edit / Delete</th>
          </tr>
          <tr v-for="(item, index) in allData" :key="index">
            <td>{{ index+1 }}</td>
            <td>{{ item.name}}</td>
            <td>{{ item.phone }}</td>
            <td>{{ item.department }}</td>
            <td>{{ item.code }}</td>
            <td><a href="">Edit</a> / <a href="#">Delete</a></td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      emp: {
        id: null,
        name: "",
        phone: "",
        department: "",
        code: "",
      },
      allData: []
    };
  },
  methods: {
    submitData() {
      var data = {
        name: this.emp.name,
        phone: this.emp.phone,
        department: this.emp.department,
        code: this.emp.code
      }
      this.allData.push(data)
      console.log(this.allData)
    }
  }
}



</script>

<style>
.inner_crud_form input,
.inner_crud_form button {
  width: 100%;
  padding: 10px 0px;
  margin-top: 15px;
}
.data_list_inner {
  width: 600px;
  padding: 50px;
  text-align: center;
  background-color: #f8f8f8;
  margin: 50px;
}
.inner_crud_form {
  width: 400px;
  padding: 50px;
  background-color: #f9f9f9;
  margin: 50px;
}
.data_list_inner table tr th,
.data_list_inner table tr td {
  padding: 10px 10px;
  border: 1px solid #000;
}
</style>