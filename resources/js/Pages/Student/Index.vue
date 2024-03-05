
<script setup>
import { usePage,useForm } from '@inertiajs/vue3';

const {students} = usePage().props
// const props = defineProps({
//  students: {
//     type:Object,
//     default: () => ({}),
//  },
// });


console.log(students)

const form = useForm({})
function destroy(id){
    if(confirm("Are you Sure to delete")){
    form.delete(route('student.destroy',id))
}
}

</script>



<template>

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <a class="nav-link active" aria-current="page" href="#">Home</a>
        <a class="nav-link" href="#">Features</a>
        <a class="nav-link" href="#">Pricing</a>
        <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
      </div>
    </div>
  </div>
</nav>

<div class="container" my-5>
<table class="table bg-dark text-white">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Name</th>
      <th scope="col">Email</th>
      <th scope="col">Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in students":key="item.id">
      <th>{{ item.id}}</th>
      <td>{{item.name}}</td>
      <td>{{item.email}}</td>
      <td>{{ item.email }}</td>
      <td><button @click="destroy(item.id)" class="btn btn-danger">Delete</button></td>
    </tr>
   
   
  </tbody>
</table>
</div>
</template>
<style>

</style>