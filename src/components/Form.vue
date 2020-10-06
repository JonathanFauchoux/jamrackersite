<template>
<div>
  <form  class="vue-form">
            <div>
                <div >
                  <label for="name">Name</label>
                    <input type="text" class="form-control" placeholder="Name" name="name" v-model="name"/>
                </div>
                <div >
                <label for="email">Email</label>
                    <input type="email" class="form-control" placeholder="Email" name="email" v-model="email"/>
                </div>
                <div class="col-8 form-group pt-2 mx-auto">
                <label for="subject">Subject</label>
                    <input type="text" class="form-control" placeholder="Subject" name="subject" v-model="subject"/>
                </div>
                <div class="">
                <label for="message">Message</label>
                    <textarea class="form-control" id="" cols="30" rows="8" placeholder="Dear Joe, ..." name="message" v-model="message"></textarea>
                </div>
                 
                <div class="">
                 
                    <a @click.prevent="retoggle" class="btn --animated">
		<span>Envoyer</span>
	</a>
                </div> 
            </div>
        </form> 
        <div v-if="errors.length" class="error-div">
          <div class="error-text">
            <h4>Merci de bien vouloir corriger:</h4>
            <ul>
              <li class="error-message" v-for="error in errors" :key="error">{{ error }}</li>
            </ul>
          </div>
        </div>  
        

</div>
  
</template>

<script>

export default {
  
  name: 'Form',
  components: {

  },
  data() {
    return {
      errors: [],
      Form: {},
      name: null,
      email: null,
      subject:null,
      message: null,
   
    }
  },
  methods:{
    retoggle(){
      this.errors = [];
      if(!this.name) this.errors.push("Nom requis.");
      if(!this.email) {
        this.errors.push("Email requis.");
      } else if(!this.validEmail(this.email)) {
        this.errors.push("Email correct requis.");        
      }
      if(!this.message) this.errors.push("message requis.");

      if(!this.errors.length && this.email !== "" && this.name!== "" && this.message!== "") {
      
       let card = document.querySelector('.card') 
      card.classList.remove('flipped')
      this.Form = {
        name: this.name,
        email: this.email,
        subject:this.subject,
        message: this.message,
      }
      this.$emit('updateDataForm',this.Form)
      this.name=""
      this.email=""
      this.subject=""
      this.message=""
      } 
      

      //console.log('Form', this.dataForm)
    },
  validEmail:function(email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@(([[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
    }
  } ,
  
  watch: {
    // watching nested property
    "email.value": function(value) {
      this.validate("email", value);
    }
  }
}
</script>

<style lang="scss" >
@import "../assets/main.scss";


.error-div{
  display: flex;
  justify-content: center;
  position: relative;
    top: -9.5rem !important;
}
.error-text h4{
  padding-bottom: 1rem;
}
.error-text ul{
  list-style: none;
  li{
    padding: .2rem;
  }
}
.vue-form {
  
  font-size: 16px;
  width:80% ;
  padding: 0 3rem;
  margin: 0 auto 4rem auto;
}



@media screen and (max-width: 768px)  {
 
  .vue-form{
    padding: 0 1rem;
    width: 90% !important;
    margin-bottom: 5rem;
  }
  .error-div{
    flex-direction: column;
    align-items: center;
    position: relative;
    top : -8.5rem !important;
    left: 2.5rem;
    
  }
  .error-text{
    margin-top: -2rem !important;
    position: relative;
    left: 3rem;
  }
  
  
  
}



.vue-form div {
  position: relative;
  margin: 20px 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 100%;
  
}
.vue-form h4,

.vue-form label {
  margin-bottom: .3rem;
  font-weight: 600;
}
.vue-form input,
.vue-form textarea,
.vue-form select,
.vue-form label {
  color: $secondary;
}
.vue-form input[type="text"],
.vue-form input[type="email"],
.vue-form textarea,
.vue-form select,
.vue-form legend {
  display: block;
  width: 100%;
  appearance: none;
  
}
.vue-form input[type="text"],
.vue-form input[type="email"],
.vue-form textarea,
.vue-form select {
  padding: 12px;
  border: 1px solid #cfd9db;
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 0.25em;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.08);
}
.vue-form input[type="text"]:focus,
.vue-form input[type="email"]:focus,
.vue-form textarea:focus,
.vue-form select:focus {
  box-shadow: 0 0 5px rgba($secondary, 0.2);
  outline: none;
  background-color: rgba(101, 243, 248, 0.6);
  box-shadow: 0px 0px 18px rgba(89, 210, 214, 0.6);
  width: 100%;
}
.vue-form .select {
  position: relative;
}

.vue-form select {
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
  cursor: pointer;
}
.vue-form select::-ms-expand {
  display: none;
}
.vue-form .vue-form-list {
  margin-top: 16px;
}
.vue-form .vue-form-list::after {
  clear: both;
  content: "";
  display: table;
}
.vue-form .vue-form-list li {
  display: inline-block;
  position: relative;
  user-select: none;
  margin: 0 26px 16px 0;
  /* float: left; */
}
.vue-form input[type="radio"] + label::before,
.vue-form input[type="radio"] + label::after,
.vue-form input[type="checkbox"] + label::before,
.vue-form input[type="checkbox"] + label::after {
  content: "";
  display: block;
  position: absolute;
  left: 0;
  top: 50%;
  margin-top: -8px;
  width: 16px;
  height: 16px;
}


.vue-form textarea {
  min-height: 120px;
  resize: vertical;
  overflow: auto;
}
.vue-form input[type="submit"] {
  border: none;
  background: #2c3e50;
  border-radius: 0.25em;
  padding: 12px 20px;
  color: #ffffff;
  font-weight: bold;
  float: right;
  cursor: pointer;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  appearance: none;
}
.no-touch .vue-form input[type="submit"]:hover {
  background: #42a2e1;
}
.vue-form input[type="submit"]:focus {
  outline: none;
  background: #2b3e51;
}
.vue-form input[type="submit"]:active {
  transform: scale(0.9);
}
.vue-form .error-message {
  height: 35px;
  margin: 0px;
}
.vue-form .error-message p {
  background: #e94b35;
  color: #ffffff;
  font-size: 1.4rem;
  text-align: center;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  border-radius: 0.25em;
  padding: 16px;
}
.vue-form .error {
  border-color: #e94b35 !important;
}



@-webkit-keyframes cd-bounce {
  0%,
  100% {
    -webkit-transform: scale(1);
  }
  50% {
    -webkit-transform: scale(0.8);
  }
}
@-moz-keyframes cd-bounce {
  0%,
  100% {
    -moz-transform: scale(1);
  }
  50% {
    -moz-transform: scale(0.8);
  }
}
@keyframes cd-bounce {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.8);
  }
}
// Btn

:root {
	--font: 1rem/1.2 "helvetica", sans-serif;
	--bg-hover: linear-gradient(
		135deg,
    #159EDE 0%,
		#2654e9 20%,
		#aa95f7 37%,
		#fff 50%,
		#fc35ca 66%,
		#7559ff 72%,
		#101ee7 100%
	);
	--btn-color: #159EDE;
}

/* formating */


/* button */
.btn {
	display: table;
	text-align: center;
	color: #ffffff;
	text-decoration: none;
	position: relative;
	font: var(--font);
	font-weight: bold;
	padding: 12px 40px;
	background-color: var(--btn-color);
	overflow: hidden;
  //margin: 24px;
  z-index: 2;
}

.--animated {
	transition: all 1s;
}

.--animated span {
	position: relative;
	z-index: 9;
}

.--animated:after {
	height: 100%;
	width: 2000px;
	transition: all 1s;
	background: var(--bg-hover);
}

.--animated:before {
	height: 26px;
	width: 100%;
	top: -50px;
	z-index: 10;
	opacity: 0;
	background-color: rgba(255, 255, 255, 0.15);
}

.--animated:hover:before {
	top: 0;
	opacity: 1;
}
.--animated:hover:after {
	left: -1750px;
}
.--animated:before,
a:after {
	position: absolute;
	top: 0;
	left: 0;
	z-index: 7;
	display: block;
	content: "";
}
.--animated:active:before {
	height: 100%;
	background-color: rgba(255, 255, 255, 0.8);
}
.--animated:active {
	transform: scale(0.95);
	transition: all 200ms;
}

</style>
