<script>
import axios from 'axios';
import StudentLine from './StudentLine';

export default {
  components: {
    StudentLine,
  },
  data() {
    return {
      students: [],
    };
    /* newStudent: '';*/
  },
  methods: {
    getAll() {
      axios.get('http://localhost:3000/students')
      .then((response) => {
        this.students = response.data;
      });
    },
    remove(index) {
      this.students.splice(index, 1);
    },
    delete() {
      axios.delete('http://localhost:3000/students/id')
      .then((response) => {
        this.students = response.data;
      });
    },
    /*addStudent: function () {
      const value = this.newStudent && this.newStudent.trim();
      if (!value) {
        return;
      }
      this.students.push({
        first_name: value,
        name: value,
        age: value,
      });
      this.newStudent = '';
    },*/
  },
  mounted() {
    this.getAll();
  },
};
</script>

<template>
  <div>
    <student-line v-for='(student, index) in students' :key="student.id" :student="student" v-on:remove="remove(index)"></student-line>
  </div>
  <!--<input class="addStudent" v-model="newStudent" @keyup.enter="addStudent">-->
</template>

<style>
</style>
