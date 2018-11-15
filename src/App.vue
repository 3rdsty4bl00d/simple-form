<template>
    <div id="all-together">
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
                            <div id="form-button">
                                <button class="btn btn-primary" @click.prevent="submitted">Next</button>
                            </div>
                        </div>
                    </div>
                </form>
            </div>
        </div>
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
                        <div class="row">
                            <div class="col-md-6 col-xs-12 col-sm-8 col-sm-offset-2 col-md-offset-3">
                                <button class="btn btn-primary proficiency-margin" @click.prevent="againnSubmitted">submit</button>
                            </div>
                        </div>

                    </div>

                </div>
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
<script>
    export default {
        data() {
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
            submitted() {
                if (this.password != this.rePassword) { 
                    alert("Your paswords doesnot match!");

                } else {
                    if(this.password.length <= 10) {
                        alert("Your password must be more than 10 characters.")
                    } else {
                        this.isSubmitted = false;
                    }
                    
                }

            },
            aggSubmitted() {
                this.agSubmitted = false;
            },
            againnSubmitted() {
                this.againSubmitted = false;
            }
        }
    }

</script>
<style>
    .panel {
        margin-top: 50px;
    }

    .top-margin {
        margin-top: 50px;
    }

    .text-area-margin {
        margin-bottom: 15px;
    }

    .gender-margin {
        margin-top: 10px;
        margin-bottom: 10px;
    }

    .address-name {
        margin-top: 10px;
        margin-bottom: 5px;
    }

    .proficiency-margin {
        margin-left: 35%
    }

</style>
