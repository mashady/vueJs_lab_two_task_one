<template>
    <div class="container mt-5">
      <h2 class="mb-3">Student Base</h2>
      <button class="btn btn-primary mb-3" @click="showAddModal = true">
        Add Student
      </button>
  
      <table class="table table-bordered">
        <thead class="table-light">
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>City</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="student in students" :key="student.id">
            <td>{{ student.id }}</td>
            <td>{{ student.name }}</td>
            <td>{{ student.city }}</td>
          </tr>
        </tbody>
      </table>
  
      <div v-if="showAddModal" class="modal fade show d-block" tabindex="-1" role="dialog" style="background-color: rgba(0,0,0,0.5);">
        <div class="modal-dialog" role="document">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title">Add Student</h5>
              <button type="button" class="btn-close" @click="showAddModal = false"></button>
            </div>
            <div class="modal-body">
              <input v-model="newStudent.id" type="number" class="form-control mb-2" placeholder="ID" />
              <input v-model="newStudent.name" type="text" class="form-control mb-2" placeholder="Name" />
              <input v-model="newStudent.city" type="text" class="form-control" placeholder="City" />
            </div>
            <div class="modal-footer">
              <button class="btn btn-secondary" @click="showAddModal = false">Cancel</button>
              <button class="btn btn-success" @click="showConfirmModal = true; showAddModal = false">Next</button>
            </div>
          </div>
        </div>
      </div>
  
      <div v-if="showConfirmModal" class="modal fade show d-block" tabindex="-1" role="dialog" style="background-color: rgba(0,0,0,0.5);">
        <div class="modal-dialog" role="document">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title">Confirm Student</h5>
              <button type="button" class="btn-close" @click="showConfirmModal = false"></button>
            </div>
            <div class="modal-body">
              <p><strong>ID:</strong> {{ newStudent.id }}</p>
              <p><strong>Name:</strong> {{ newStudent.name }}</p>
              <p><strong>City:</strong> {{ newStudent.city }}</p>
            </div>
            <div class="modal-footer">
              <button class="btn btn-secondary" @click="showAddModal = true; showConfirmModal = false">Edit</button>
              <button class="btn btn-primary" @click="addStudent">Confirm</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'StudentTable',
    data() {
      return {
        students: [
          { id: 1, name: 'Ali', city: 'Cairo' },
          { id: 2, name: 'Sara', city: 'Alexandria' },
        ],
        newStudent: { id: '', name: '', city: '' },
        showAddModal: false,
        showConfirmModal: false,
      };
    },
    methods: {
      addStudent() {
        this.students.push({ ...this.newStudent });
        this.newStudent = { id: '', name: '', city: '' };
        this.showConfirmModal = false;
      },
    },
  };
  </script>
  