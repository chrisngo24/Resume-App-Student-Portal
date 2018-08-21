<template>
  <div class="home container">
    <h1>{{ message }}</h1>
    <div class="resume-body">
      <img class="photo" v-bind:src="photo" width="300" alt="Card image cap">
      <h3>Name: {{ first_name }} {{ last_name }}</h3>
      <h4>Email: {{ email }}</h4>
      <h5>Phone: {{ phone_number }}</h5>
      <h6>Bio: {{ short_bio }}</h6>
      <ul>
        <li>LinkedIn: {{ linkedin_url }}</li>
        <li>Twitter: {{ twitter_handle }}</li>
        <li>Github: {{ github_url }}</li>
        <li>Resume: {{ resume }}</li>
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
      short_bio: "My name is Jenny!, I'm from the block", 
      linkedin_url: "LinkedIn URL",
      twitter_handle: "Twitter URL",
      personal_blog: "Blog URL", 
      online_resume_url: "Resume Page", 
      github_url: "Github URL",
      photo: "https://m.media-amazon.com/images/M/MV5BMTY0OTY3ODA3OV5BMl5BanBnXkFtZTcwMzMyMzQ1NQ@@._V1_UY317_CR32,0,214,317_AL_.jpg"
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>