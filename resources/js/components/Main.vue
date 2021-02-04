<template>
        <div style="background-color: rgb(82,81,81);">
            <b-navbar id="menu-main" toggleable="lg" type="light" variant="light">
            <!-- <b-navbar-brand href="#">NavBar</b-navbar-brand> -->

                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>  
                </b-navbar-nav>

                <!-- Right aligned nav items -->
                <b-navbar-nav class="m-auto">
                    <b-nav-item id="capital" v-on:click="home" class="nav-one" href="" ><b style="color: rgb(242, 240, 237) !important;">Home</b></b-nav-item>
                    <!-- <b-nav-item id="capital" href=""><b style="color: rgb(242, 240, 237) !important;">Certificates</b></b-nav-item> -->
                    <!-- <b-nav-item id="capital" href=""><b style="color: rgb(242, 240, 237) !important;">Experience</b></b-nav-item> -->
                    <b-nav-item id="capital" href=""><b style="color: rgb(242, 240, 237) !important;">Projects</b></b-nav-item>
                    <!-- <b-nav-item id="capital" href=""><b style="color: rgb(242, 240, 237) !important;">Hobby</b></b-nav-item> -->
                    <b-nav-item id="capital" href=""><b style="color: rgb(242, 240, 237) !important;">Reviews</b></b-nav-item>
                </b-navbar-nav>

                <b-navbar-nav class="m-right">
                    <b-nav-item href=""><img :src="flag_myan" width="28" height="28"></b-nav-item>
                </b-navbar-nav>
                </b-collapse>
            </b-navbar>
            <transition name="fade">
            <div v-show="active">
                <b-jumbotron bg-variant="light" id="jum" text-variant="white" border-variant="dark">
                    <h1 style="text-shadow: 2px 2px rgb(82,81,81) !important; font-size: 60px; opacity: 0.8;">MORPHIN Tech</h1>
                     <div class="col-md-12 d-flex justify-content-center">
                        <div class="line" style="border-top: 4px solid rgb(237,232,227, 0.8); border-radius: 50%; width: 20%; text-align:center;"></div>
                    </div>
                    <h3 class="pt-1" style="text-shadow: 2px 2px rgb(82,81,81) !important; font-size: 35px; opacity: 0.8;">WEB DEVELOPMENT</h3>
                    <div class="cp" style="display: inline-block; border-radius: 20%; margin-top: 38px !important;">
                        <b-button type="button" variant="outline-light" v-on:click="cp" class="checkpro">CHECK PROFILE</b-button>
                    </div>
                </b-jumbotron>
            </div>
            </transition>
            <transition name="fade">
            <div class="col-md-12" v-show="active_one" style="display:none;">
                <div class="row profile">
                    <div class="col-md-4 mt-4 d-flex justify-content-center">
                        <img :src="image_src" width="300" height="350" class="profile-image">
                    </div>
                    <div class="col-md-8">
                        <div class="card mt-4" id="profile-card">
                            <div class="card-body">
                                <!-- <div class="row">
                                    <div class="col-md-6">
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Name : <strong class="pl-1" style="font-wieight: normal !important;">Thi Ha Aung</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Birthday : <strong class="pl-1">18.5.1998</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />NRC : <strong class="pl-1">12/OuKaTa (N) 190591</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Religion : <strong class="pl-1">Buddhist</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Blood Type : <strong class="pl-1">( B )</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Height : <strong class="pl-1">5'6"</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Nationality : <strong class="pl-1">Bamar ( Myanmar )</strong></p>
                                    </div>
                                    <div class="col-md-6">
                                        <section class="section">
                                             <p class="date shadow_one" v-text="currentDate"></p>
                                            <p class="time shadow" v-text="currentTime"></p>
                                        </section>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Father Name : <strong class="pl-1">U Aung Moe Khaing</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Mother Name : <strong class="pl-1">Daw Aye Aye Khaing</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94);" />Phone : <strong class="pl-1">+959795864194</strong></p>
                                        <p class="text-p"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 14px; color: rgb(52, 209, 94); text-transform: lowercase !important;" />Gmail : <strong class="pl-1" style="text-transform: lowercase !important;">thihaeung@gmail.com</strong></p>
                                    </div>
                                </div>
                                <div class="col-md-12">
                                    <p class="text-p" style="text-align:center;"><font-awesome-icon icon="circle" class="pr-1" style="font-size: 16px; color: rgb(52, 209, 94);" />Address : <strong class="pl-1">No.28 Mya Street, KyikeKaSan W.d, Bahan T.S, Yangon</strong></p>
                                </div> -->
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            </transition>
            <!-- <div class="col-md-12 d-flex justify-content-center">
                <div class="line mt-3" style="border-top: 4px solid rgb(253,253,255, 0.8); border-radius: 50%; width: 20%; text-align:center;"></div>
            </div> -->
            <!-- <div class="col-md-12" style="display: none;">
                <div class="col-12 d-flex justify-content-center" style="text-align:center;">
                    <h1 class="ml-2" style="color: rgb(253,253,255, 0.8); text-shadow: 2px 3px rgb(82,81,81);
                     border-radius: 50%; letter-spacing: 4px; font-family: 'Bebas Neue', cursive; max-width: 390px; text-align:center; font-size: 40px;">CERTIFICATES</h1>
                </div>
                <div style="margin-top: 60px !important;">
                    <div class="row d-flex justify-content-center" style="text-align:center;">
                        <div class="col-md-6">
                            <img src="/c1.jpg" alt="" width="450" height="600" style="transform: rotate(-20deg); box-shadow: 2px 2px 10px rgb(82,81,81);">
                        </div>
                        <div class="col-md-6">
                            <img src="/c2.jpg" alt="" width="450" height="600" style="transform: rotate(20deg); box-shadow: 2px 2px 10px rgb(82,81,81);">
                        </div>
                    </div>
                </div>
            </div> -->
            <div class="col-md-12">
                 <div class="col-12 d-flex justify-content-center" style="text-align:center;">
                    <h1 class="ml-2" style="color: rgb(253,253,255, 0.8); text-shadow: 2px 3px rgb(82,81,81);
                     border-radius: 50%; letter-spacing: 4px; font-family: 'Bebas Neue', cursive; max-width: 390px; text-align:center; font-size: 40px;">PROJECTS</h1>
                </div>
                <div class="mt-4">
                    <b-jumbotron class="b-jump" style="font-family: 'Noto Sans', sans-serif; background-image: url('/Challenger 11 BG-01.png'); background-size: cover;" >
                        <div class="d-flex justify-content-center">
                            <div class="col-md-3">
                                <img src="/Challenger 11 Logo White.png" alt="" width="150" height="110" style="margin-top: 30px; text-align:center;">
                            </div>
                            <div class="col-md-9">
                                <h1 style="font-size: 60px; color: #fff;">FOOTBALL GAME</h1>
                                <p style="color: #fff;">Challenger11.com is a formation creator for football fans to build
                                custom games. Create your own football team with your favorite players. Share the best tactics and players with your friends.</p>
                                <b-button variant="outline-light" style="font-size: 20px; border-bottom-left-radius: 26px; border-top-left-radius: 26px;border-top-right-radius: 26px;
                                border-bottom-right-radius: 26px;border-bottom-left-radius: 26px; border-top-left-radius: 26px;
                                border-top-right-radius: 26px;border-bottom-right-radius: 26px;" href="https://www.challenger11.com/">Visit Site</b-button>
                            </div>
                        </div>
                    </b-jumbotron>
                     <!-- <b-jumbotron class="b-jump" style="font-family: 'Noto Sans', sans-serif; background-image: url(''); background-size: cover;" >
                        <div class="d-flex justify-content-center">
                            <div class="col-md-3">
                                <img src="/Challenger 11 Logo White.png" alt="" width="150" height="110" style="margin-top: 30px; text-align:center;">
                            </div>
                            <div class="col-md-9">
                                <h1 style="font-size: 60px; color: #fff;">FOOTBALL GAME</h1>
                                <p style="color: #fff;">Challenger11.com is a formation creator for football fans to build
                                custom games. Create your own football team with your favorite players. Share the best tactics and players with your friends.</p>
                                <b-button variant="outline-light" style="font-size: 20px; border-bottom-left-radius: 26px; border-top-left-radius: 26px;border-top-right-radius: 26px;
                                border-bottom-right-radius: 26px;border-bottom-left-radius: 26px; border-top-left-radius: 26px;
                                border-top-right-radius: 26px;border-bottom-right-radius: 26px;" href="https://www.challenger11.com/">Visit Site</b-button>
                            </div>
                        </div>
                    </b-jumbotron>
                     <b-jumbotron class="b-jump" style="font-family: 'Noto Sans', sans-serif; background-image: url(''); background-size: cover;" >
                        <div class="d-flex justify-content-center">
                            <div class="col-md-3">
                                <img src="/Challenger 11 Logo White.png" alt="" width="150" height="110" style="margin-top: 30px; text-align:center;">
                            </div>
                            <div class="col-md-9">
                                <h1 style="font-size: 60px; color: #fff;">FOOTBALL GAME</h1>
                                <p style="color: #fff;">Challenger11.com is a formation creator for football fans to build
                                custom games. Create your own football team with your favorite players. Share the best tactics and players with your friends.</p>
                                <b-button variant="outline-light" style="font-size: 20px; border-bottom-left-radius: 26px; border-top-left-radius: 26px;border-top-right-radius: 26px;
                                border-bottom-right-radius: 26px;border-bottom-left-radius: 26px; border-top-left-radius: 26px;
                                border-top-right-radius: 26px;border-bottom-right-radius: 26px;" href="https://www.challenger11.com/">Visit Site</b-button>
                            </div>
                        </div>
                    </b-jumbotron> -->
                </div>
            </div>
            <div class="col-md-12">
                <div class="col-12 d-flex justify-content-center" style="text-align:center;">
                    <h1 class="ml-2" style="color: rgb(253,253,255, 0.8); text-shadow: 2px 3px rgb(82,81,81);
                     border-radius: 50%; letter-spacing: 4px; font-family: 'Bebas Neue', cursive; max-width: 390px; text-align:center; font-size: 40px;">REVIEWS</h1>
                </div>
            </div>
        </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Merriweather+Sans:wght@500&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@1,700&display=swap');

b-jumbotron[header]{
    font-family: 'Noto Sans', sans-serif !important;
}

.fade-leave-active {
    animation: none;
}

#menu-main
{
    background-color: rgb(82, 81, 81) !important;
    box-shadow: 0px 0px 11px rgb(233,236,239);
}

#carousel-fade{
    width: 500px;
    height: 500px;
}

#capital{
    text-transform: uppercase;
    font-family: 'Bebas Neue', cursive;
    font-size: 22px;
    font-weight: bold;
    letter-spacing: 2px;
    transition-duration: 1s;
}

.profile-image{
     box-shadow:  0 01px rgb(82,81,81),
                 01px 0 rgb(82,81,81),
                 01px 02px rgb(82,81,81),
                 02px 01px rgb(82,81,81),
                 02px 03px rgb(82,81,81),
                 03px 02px rgb(82,81,81),
                 03px 04px rgb(82,81,81),
                 04px 03px rgb(82,81,81),
                 04px 05px rgb(82,81,81),
                 05px 04px rgb(82,81,81),
                 05px 06px rgb(82,81,81),
                 06px 05px rgb(82,81,81);
}

.profile-image:hover{
    transform: perspective(1000px) rotateY(-45deg);
    transition-duration: 0.9s;
}

#profile-card{
    border: 2px solid rgb(82,81,81) !important;
    background-color: rgb(82,81,81);
    box-shadow: 2px 2px 5px rgb(82,81,81);
}
#capital:hover{
    transform: scale(1.2) !important;
}

b-nav-item {
    color: rgb(242, 240, 237) !important;
}

#iconOne{
    color: rgb(164,102,42);
}

#iconTwo{
    color: rgb(4,115,183);
}

#iconThree{
    color: rgb(241,203,110);
}

#iconFour{
    color: rgb(44,92,45);
}

#iconFive{
    color: rgb(165,39,33);
}

header {
    border: 2px solid #000 !important;
}
.checkpro{
    border-color: #fff !important;
    /* background-color: rgb(82,81,81); */
    color: #fff;
    box-shadow: 2px 2px 5px rgb(82,81,81);
    /* border-bottom-left-radius: 26px;
    border-top-left-radius: 26px;
    border-top-right-radius: 26px;
    border-bottom-right-radius: 26px; */
    font-family: 'Bebas Neue', cursive;
    border-radius: 0%;
    font-size: 25px;
    transition: .5s ease;    /* font-weight: bold; */
}

.checkpro:hover{
    background: none;
    color: #fff;
    border-color: #fff !important;
    background-color: rgb(82,81,81);
}

#jum{
   border: none !important;
   border-radius: 0%;
   color: #fff !important;
   text-align: center !important;
   background-image: url('https://i.imgur.com/zy1JbiK.jpg') !important;
   background-size: cover !important;
   background-repeat: no-repeat !important;
    font-family: 'Merriweather Sans', sans-serif;
}

.text-p{
    /* font-weight: bold; */
    /* text-shadow: 2px 2px 9px rgb(55,50,50); */
    color: #fff;
    border-bottom: 1px solid #fff;
    cursor: pointer;
    text-transform: capitalize;
    font-family: 'Merriweather Sans', sans-serif;
    opacity: 0.9;
    font-weight: normal !important;
    letter-spacing: 1px;
    font-size: 14px;
    font-style: normal !important;
}

.time {
  font-size: 23px;
  border: 2px solid #525151;
  border-top-right-radius: 25px;
  border-bottom-right-radius: 25px;
  border-top-left-radius: 25px;
  border-bottom-left-radius: 25px;
  text-align:center;
  font-weight: bold;
  font-family: 'Merriweather Sans', sans-serif;
}

.date {
  font-size: 20px;
  border: 2px solid #525151;
  border-top-right-radius: 25px;
  border-bottom-right-radius: 25px;
  border-top-left-radius: 25px;
  border-bottom-left-radius: 25px;
  text-align:center;
  font-weight: bold;
  font-family: 'Merriweather Sans', sans-serif;
}

.shadow_one{
    background: linear-gradient(to left, #525151, #d7d2cc);
}
.shadow {
  text-shadow: 2px 2px rgb(254,254,254, 0.5);
  background: linear-gradient(to right, #525151, #d7d2cc); 
}

.b-jump{
    box-shadow: 2px 2px 10px rgb(51,51,51);
    border-radius: 0%;
}


</style>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        },
        data: function() {
            return {
                image_src: '/pro.jpeg',
                flag_myan: '/myanmar.png',
                currentTime: null,
                currentDate: null,
                active: true,
                active_one: false
            }
        },
        methods: {
                cp: function (event) {
                  this.active = false;
                  this.active_one = true;
                },
                home: function (event) {
                  this.active = true;
                  this.active_one = false;
                },
                updateCurrentTime() {
                    this.currentTime = moment().format('LTS');
                    console.log(this.currentTime);
                },
                updateCurrentDate() {
                    this.currentDate = moment().format('dddd, MMMM Do YYYY');
                    console.log(this.currentDate);
                }
        },
        created() {
            this.currentTime = moment().format('LTS');
            setInterval(() => this.updateCurrentTime(), 1 * 1000);
            this.currentDate = moment().format('MM/DD/YYYY');
            setInterval(() => this.updateCurrentDate(), 1 * 1000);
        }
    }
    
</script>
