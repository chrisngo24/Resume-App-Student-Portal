<template>
  <div class="home container">
    <h1>{{ message }}</h1>
      <div class="card" style="width: 25rem;" v-for="student in students">
        <h5 class="card-header">Featured</h5>
        <div class="card-body">
          <img class="photo" v-bind:src="photo" width="300" alt="Card image cap">
          <div class="card">
          <h3 class="card-title">Name: {{ student.first_name }} {{ student.last_name }}</h3>
          <h4>Email: {{ student.email }}</h4>
            <h5>Phone: {{ student.phone_number }}</h5>
            <h6>Bio: {{ student.short_bio }}</h6>
          </div>
            <div class="card"><label>Education: {{ student.education }}</label></div>
            <div class="card"><label>Experience: {{ student.experiences }}</label></div>
            <div class="card"><label>Skills: {{ student.skills }}</label></div>
            <div class="card">
            <ul>
              <li>LinkedIn: {{ student.linkedin_url }}</li>
              <li>Twitter: {{ student.twitter_handle }}</li>
              <li>Github: {{ student.github_url }}</li>
              <li>Resume: {{ student.resume }}</li>
            </ul>
          </div>
          <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
          Update Your Resume
        </button>
        </div>
      </div>
    <div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Update Resume</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <form v-on:submit.prevent="submit()">
                    <h1>Edit Profile</h1>
                    <ul>
                      <li class="text-danger" v-for="error in errors">{{ error }}</li>
                    </ul>
                    <div class="form-group">
                      <label>First Name:</label> 
                      <input type="text" class="form-control" v-model="first_name">
                    </div>
                    <div class="form-group">
                      <label>Last Name:</label> 
                      <input type="text" class="form-control" v-model="last_name">
                    </div>
                    <div class="form-group">
                      <label>Email:</label> 
                      <input type="text" class="form-control" v-model="email">
                    </div>
                    <div class="form-group">
                      <label>Short Bio</label> 
                      <input type="text" class="form-control" v-model="short_bio">
                    </div>
                    <div class="form-group">
                      <label>Linked In URL</label> 
                      <input type="text" class="form-control" v-model="linkedin_url">
                    </div>
                    <div class="form-group">
                      <label>Twitter Handle</label> 
                      <input type="text" class="form-control" v-model="twitter_handle">
                    </div>
                    <div class="form-group">
                      <label>Personal Blog</label> 
                      <input type="text" class="form-control" v-model="personal_blog">
                    </div>
                    <div class="form-group">
                      <label>Online Resume URL</label> 
                      <input type="text" class="form-control" v-model="online_resume_url">
                    </div>
                    <div class="form-group">
                      <label>Github URL</label> 
                      <input type="text" class="form-control" v-model="github_url">
                    </div>
                    <div class="form-group">
                      <label>Image (optional):</label>
                      <input type="text" class="form-control" v-model="photo">
                    </div>
                    <input type="submit" class="btn btn-primary" value="Submit">
              </form>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
</style>

<script>
var axios = require("axios");

export default {
  data: function() {
    return {
      message: "Your Resume",
      students: [],
      student: {},
      first_name: "",
      last_name: "", 
      email: "", 
      phone_number: "", 
      short_bio: "", 
      linkedin_url: "",
      twitter_handle: "",
      personal_blog: "", 
      online_resume_url: "", 
      github_url: "",
      photo: "https://www.telegraph.co.uk/content/dam/beauty/2017/07/19/TELEMMGLPICT000133558777_trans_NvBQzQNjv4BqAYbq1paTAozN9Q6uyiXH5hBUClMeQ3MJ58n6bA-Dqyg.jpeg?imwidth=480", 
      errors: []
    };
  },
  created: function() {
    axios.get("https://vue-tang-resume-api.herokuapp.com/students").then(
      function(response) {
        console.log(response);
        this.students = response.data;
      }.bind(this)
    );
  },
  methods: {
    submit: function() {
      var params = {
        first_name: this.first_name,
        last_name: this.last_name,
        email: this.email,
        phone_number: this.phone_number,
        short_bio: this.short_bio,
        linkedin_url: this.linkedin_url,
        twitter_handle: this.twitter_handle,
        personal_blog: this.personal_blog,
        online_resume_url: this.online_resume_url,
        github_url: this.github_url,
        photo: this.photo,
      };
    },
  }
};
</script>