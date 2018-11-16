<!--
      this is the template of html
      with the help of template we
      can use vue.js
  -->
<!--
      note to remember:
      ==> the parts inside the template file
      should be wrapped inside one div
      ==> there will occur an error
      if there two or more than two
      elements
      ==>here vue.js directives are used
            like
                v-model: it will give you two way binding
                v-model.lazy: it will upload your data once you finished inputing it
                v-if: you know the drill
                v-else: again it's the same
                    but the (v-if v-else) must be 
                    in the consecutive same type element
                v-on:click or @click: it will give you direction to 
                                        the attached vue.js function
      ==>here bootstrap is used
          the bootstrap that i used is max bootstrap
          i have used it with the help of a cdn link
      ==>the classes that i used are
          form-control
          from-group
          panel
          panel-default
          panel=heading
          panel-body
          ==> these bootstrap classes will help 
              to make the form look better
      ==>also the column classes are
         ==> these are all from left side
              col-sm-8: for small devices
              col-xs-12: for extra small devices
              col-md-6: for medium devices
         ==> these are from right side
             col-sm-offset-2: for small devices
             col-md-offset-3: for medium devices
         ==> this will help you keep you data 
             or form right in the exact middle
  -->
  
  <!--
      ================================
      ********************************
      ================================
      ********************************
      this was created by 3rdsty4bl00d
      name == > Shivam Shrestha
      ********************************
      ================================
      ********************************
      ================================
  -->
  
<template>
    <div id="all-together">
        <!--
           this is the first check of the form
       -->
        <!--
           it contains 
           first name
           lastname
           email
           password of the user
       -->
        <div id="please-fill-the-form" v-if="isSubmitted">
            <div class="container">
                <form action="userFirstForm" class="top-margin">
                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3">
                            <!--Header of the form-->
                            <h3 class="text-center">Please fill the form!</h3>
                            <hr>
                            <!--Introduction of user-->
                            <div class="form-group">
                                <label for="name">
                                    First Name
                                </label>
                                <input type="text" id="first-name" class="form-control" v-model.lazy="firstName">
                            </div>
                            <div class="form-group">
                                <label for="name">
                                    Last Name
                                </label>
                                <input type="text" id="last-name" class="form-control" v-model.lazy="lastName">
                            </div>
                            <div class="form-group">
                                <label for="email">
                                    Email
                                </label>
                                <input type="text" id="email" class="form-control" v-model.lazy="email">
                            </div>
                            <div class="form-group">
                                <label for="password">
                                    Password
                                </label>
                                <input type="password" id="password" class="form-control" v-model.lazy="password">
                            </div>
                            <div class="form-group">
                                <label for="password">
                                    Re-type Password
                                </label>
                                <input type="password" id="re-password" class="form-control" v-model.lazy="rePassword">
                            </div>
                            <!--
                                this is a button called next
                                it takes the user to next page called
                                some more
                                which asks for more user data
                            -->
                            <div id="form-button">
                                <button class="btn btn-primary" @click.prevent="submitted">Next</button>
                            </div>
                        </div>
                    </div>
                </form>
            </div>
        </div>
        <!--second page of the form
            here it contains
            age
            gender
            and
            address of the user
            -->
        <!--
                here isSubmitted is the function used to 
                see if the v-else will activate or not.
                agSubmitted has the same functionality.
                -->
        <!--
                also a button called next
                which takes the user to another page
                called 'your proficiency?'
                which will ask what the user proficiency has
            -->
        <div id="form-second" v-else="isSubmitted = !isSubmitted">
            <div id="some-more" v-if="agSubmitted">
                <div class="container">
                    <form action="userSecondForm" class="top-margin">
                        <div class="row">
                            <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3">
                                <!--heading-->
                                <h3 class="text-center">Some More!</h3>
                                <hr>
                                <div class="form-group">
                                    <label for="age">
                                        Age
                                    </label>
                                    <input type="text" id="age" class="form-control" v-model.number="age">
                                </div>
                                <div class="row">
                                    <div class="col-md-6 gender-margin">
                                        <label for="gender">Gender</label>
                                    </div>
                                </div>
                                <label for="male">
                                    <input type="radio" id="male" value="Male" v-model.lazy="gender">
                                    Male
                                </label>
                                <label for="female">
                                    <input type="radio" id="female" value="Female" v-model.lazy="gender">
                                    Female
                                </label>
                                <label for="other">
                                    <input type="radio" id="other" value="Other" v-model.lazy="gender">
                                    Other
                                </label>
                                <div class="row form-group">
                                    <div class="col-md-6 address-name">
                                        <label for="address">
                                            Address
                                        </label>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-md-12 text-area-margin">
                                        <textarea id="address" cols="100" rows="5" class="form-control" v-model.lazy="address"></textarea>
                                    </div>
                                </div>
                                <div id="form-button-2" class="form-group">
                                    <button class="btn btn-primary" @click.prevent="aggSubmitted">Next</button>
                                </div>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
            <!--
                this is the proficiency part
                proficiency: having certain skill
                here I built a form that gives the information 
                of a user at what skill set he/she has
                like
                front-end developer
                back-end developer
                java developer
                graphics designer
                android developer
                ios developer
            -->
            <!--
                also a button called submit
                that takes the user to another page
                that gives the information about the user
                which he/she just filled
            -->
            <div id="your-proficiency" v-else="agSubmitted = !agSubmitted">
                <div id="proficient" v-if="againSubmitted">
                    <div class="container">
                        <form action="proficiency">
                            <div class="row">
                                <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3">
                                    <div class="form-group">
                                        <!--heading-->
                                        <h3 class="text-center">Your Proficiency?</h3>
                                        <hr>
                                        <label for="front-end-development" class="proficiency-margin">
                                            <input type="checkbox" id="front-end-development" value="Front-End Developer" v-model.lazy="proficiency">
                                            Front-End Developer
                                        </label>
                                        <br>
                                        <label for="back-end-development" class="proficiency-margin">
                                            <input type="checkbox" id="back-end-development" value="Back-End Developer" v-model.lazy="proficiency">
                                            Back-End Developer
                                        </label>
                                        <br>
                                        <label for="java-development" class="proficiency-margin">
                                            <input type="checkbox" id="java-development" value="Java Developer" v-model.lazy="proficiency">
                                            Java Developer
                                        </label>
                                        <br>
                                        <label for="graphics-designer" class="proficiency-margin">
                                            <input type="checkbox" id="graphics-designer" value="Graphics Designer" v-model.lazy="proficiency">
                                            Graphics Designer
                                        </label>
                                        <br>
                                        <label for="android-developer" class="proficiency-margin">
                                            <input type="checkbox" id="android-developer" value="Android Developer" v-model.lazy="proficiency">
                                            Android Developer
                                        </label>
                                        <br>
                                        <label for="ios-development" class="proficiency-margin">
                                            <input type="checkbox" id="ios-development" value="IOS Developer" v-model.lazy="proficiency">
                                            IOS Developer
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </form>
                        <!--
                            this is the button
                            called submit
                        -->
                        <div class="row">
                            <div class="col-md-6 col-xs-12 col-sm-8 col-sm-offset-2 col-md-offset-3">
                                <button class="btn btn-primary proficiency-margin" @click.prevent="againnSubmitted">submit</button>
                            </div>
                        </div>
                    </div>
                </div>
                <!--
                    this is the page to show the 
                    user information
                    it contains 
                    first name
                    last name
                    email
                    password
                    age
                    gender
                    address
                    proficiency
                -->
                <div id="your-data" v-else="againSubmitted = !againSubmitted">
                    <div class="container">
                        <div class="row">
                            <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3">
                                <div class="panel panel-default">
                                    <div class="panel-heading">
                                        <h3>Your Data</h3>
                                    </div>
                                    <div class="panel-body">
                                        <p>First Name: {{ firstName }}</p>
                                        <p>Last Name: {{ lastName }}</p>
                                        <p>Email: {{ email }}</p>
                                        <p>Password: {{ password }}</p>
                                        <hr>
                                        <p>Age: {{ age }}</p>
                                        <p>Gender: {{ gender }}</p>
                                        <p style="white-space: pre">Address: {{ address }}</p>
                                        <hr>
                                        <p>Proficiency:</p>
                                        <ul>
                                            <li v-for="course in proficiency">{{ course }}</li>
                                        </ul>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<!--
    this is the script tag of above html
    in this sript tag 
    I have used javascript
    more specifically, vue.js, i.e
    framework of javascript 
-->
<!--
    feel free to edit it
    as you like
-->
<script>
    export default {
        data() {
            /*
                this is the data
                all the data is stored here in this function
            */
            return {
                isSubmitted: true,
                agSubmitted: true,
                againSubmitted: true,
                firstName: '',
                lastName: '',
                email: '',
                password: '',
                rePassword: '',
                age: '',
                gender: '',
                address: '',
                proficiency: []
            }
        },
        methods: {
            /*
                these are all the functions
                that is called by html file
                that is above 
            */
            submitted() {
                /*
                    this is the first page
                    function call
                    called by next button of the page
                    called by button of 'please fill your form! page
                */
                if (this.password != this.rePassword) {
                    /*
                        this checks the password 
                        that is 
                        password and re-typer password
                        if they donot match it will alert the user
                        'your passwords doesnot match'
                    */
                    alert("Your paswords doesnot match!");
                } else {
                    /*
                        this will check if the user inputed 
                        the password that is less than 10 characters
                    */
                    if (this.password.length <= 10) {
                        alert("Your password must be more than 10 characters.")
                    } else {
                        /*
                            once everything is right
                            isSubmitted will be true
                            only then can we
                            move on to next page
                        */
                        this.isSubmitted = false;
                    }
                }
            },
            aggSubmitted() {
                /*
                    this is the second page
                    function call
                    called by next button of the page
                    called by button of some more page
                */
                this.agSubmitted = false;
            },
            againnSubmitted() {
                /*
                    this is the third page
                    function call
                    called by submit button of the page
                    called by button of your proficiency? page
                */
                this.againSubmitted = false;
            }
        }
    }

</script>
<!--
    this is the style
    all the css is written here
    here 
    classes are activated with the help of dot(.)
    and id's are activated with the help of hash(#)
    feel free to edit it as you like
-->
<style>
    .panel {
        /*
            gives the top margin
            50px of gaping
            above the heading
            this is the margin of your data page
        */
        margin-top: 50px;
    }

    .top-margin {
        /*
            this is the margin of the second form
        */
        margin-top: 50px;
    }

    .text-area-margin {
        /*
            this is the margin
            of address name
            it is the bottom margin
        */
        margin-bottom: 15px;
    }

    .gender-margin {
        /*
            it is the gernder
            margin
            both top and bottom
        */
        margin-top: 10px;
        margin-bottom: 10px;
    }

    .address-name {
        /*
            this is the margin of 
            textarea address
        */
        margin-top: 10px;
        margin-bottom: 5px;
    }

    .proficiency-margin {
        /*
            this is the margin of proficiency
        */
        margin-left: 35%
    }

</style>
