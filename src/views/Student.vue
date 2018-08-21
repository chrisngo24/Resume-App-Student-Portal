<template>
  <div class="home container">
    <h1>{{ message }}</h1>
    <div class="resume-body">
      <img class="photo" v-bind:src="photo" width="300" alt="Card image cap">
      <h3>Name: {{ first_name }} {{ last_name }}</h3>
      <h4>Email: {{ email }}</h4>
      <h5>Phone: {{ phone_number }}</h5>
      <h6>Bio: {{ bio }}</h6>
      <ul>
        <li>{{ linkedin }}</li>
        <li>{{ twitter }}</li>
        <li>{{ github }}</li>
        <li>{{ resume }}</li>
        <li>{{ linkedin }}</li>
      </ul>
    </div>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
    Update Your Resume
  </button>
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
            SAMPLE CODE TO UPDATE
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Your Resume",
      first_name: "Jenny",
      last_name: "Lopez", 
      email: "jenny@email.com", 
      phone_number: "(555) 867-5309", 
      bio: "My name is Jenny!, I'm from the block", 
      linkedin: "URL",
      twitter: "URL",
      website: "URL", 
      resume: "URL", 
      github: "URL",
      photo: "https://m.media-amazon.com/images/M/MV5BMTY0OTY3ODA3OV5BMl5BanBnXkFtZTcwMzMyMzQ1NQ@@._V1_UY317_CR32,0,214,317_AL_.jpg"
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>