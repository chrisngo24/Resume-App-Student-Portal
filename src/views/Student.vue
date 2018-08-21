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
      // will implement once backend is complete
    //   axios
    //     .post("http://localhost:3000/api/expenses", params)
    //     .then(response => {
    //       this.$router.push("/home");
    //     })
    //     .catch(error => {
    //       this.errors = error.response.data.errors;
    //     });
    // }
    
    },
  }
};
</script>