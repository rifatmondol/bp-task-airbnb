<template>
    <div class="host-part">
        <h4>Meet you host</h4>
        <div class="host-main mt-4">
            <div class="row">
                <div class="offset-lg-2 offset-md-1 offset-sm-1 col-lg-8 col-sm-10 col-md-10">
                    <div class="row">
                        <!-- Host profile -->
                        <div class="col-md-12">
                            <a href="#" class="text-decoration-none text-black">
                                <div class="host-information">
                                    <div class="row">
                                        <div class="col-md-8 col-8">
                                            <div class="host-image text-center">
                                                <div class="img"><img src="@/assets/images/host-photo.webp" alt="host"></div>
                                                <h3>Sagrario</h3>
                                                <p>Superhost</p>
                                            </div>
                                        </div>
                                        <div class="col-md-4 col-4">
                                            <div class="host-details">
                                                <div class="details-list" v-for="detail in details" :key="detail.id">
                                                    <h3 v-html="detail.title"></h3>
                                                    <span>{{ detail.subtitle }}</span>
                                                    <div class="hrline" v-html="detail.line"></div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </a>
                        </div>
                        <!-- Host other information -->
                        <div class="col-md-12 mt-4">
                            <div class="host-other-details mt-3" v-for="otherDetail in otherDetails" :key="otherDetail.id">
                                <span class="me-3"><img :src="otherDetail.imgSrc" alt="images"></span>
                                <p>{{ otherDetail.title }}</p>
                            </div>
                            <div class="show-more mt-4">
                                <p>Open and communicative, with donation of people and happy to welcome friends from the world at home.</p>
                                <a href="#" class="d-inline-block mb-4">Show more <i class="fa-solid fa-angle-right"></i></a> <br>
                                <button class="btn-host mb-2">Message Host</button>
                                <div class="hrline my-4"><hr></div>
                                <span>To protect your payment, never transfer money or communicate outside of the Airbnb website or app.</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Host about -->
        <div class="host-about-place mt-5">
            <div class="show-more">
                <h4>About this place</h4>
                <p class="mt-3">Nice and spacious room in the heart of Valencia, with double bed and a balcony. Silent because there is no traffic. Surrounded by all the landmarks , museums , cathedral , leisure, and close to the beach where you can go by bike, bus , tram or car if your means of transportation. <br>
                I would love to receive people wanting to enjoy my city and help in what I can .</p>
                <a href="#" class="d-inline-block mb-4">Show more <i class="fa-solid fa-angle-right"></i></a> <br>
            </div>
            <div class="hrline my-4"><hr></div>
        </div><!-- Host about -->
        
        <!-- Host Sleep -->
        <div class="host-sleep mt-5">
            <h4>Where you'll sleep</h4>
            <div class="sleep-details mt-4">
                <span class="mb-3 d-block"><img src="@/assets/images/bed.png" alt="bed image"></span>
                <h6>Bedroom</h6>
                <p class="mb-0">1 double bed</p>
            </div>
            <div class="hrline my-5"><hr></div>
        </div><!-- Host Sleep -->
        
        <!-- Offer Place -->
        <div class="host-offer mt-5" id="amenities">
            <h4 class="mb-4">What this place offers</h4>
            <div class="row">
                <div class="col-lg-6 col-md-12 col-sm-6" v-for="offer in offers" :key="offer.id">
                    <div class="offer-details mb-3">
                        <span class="me-3"><img :src="offer.imgSrc" alt="image"></span>
                        <p class="mb-0">{{offer.title}}</p>
                    </div>
                </div>
            </div>
            <button class="offer-btn mt-4">Show all 37 amenities</button>
            <div class="hrline my-5"><hr></div>
        </div><!-- Offer Place -->

         <!-- Calendar Full-->
         <div class="date-section">
            <h4>Select check-in date</h4>
            <p class="mb-4">Add your travel dates for exact pricing</p>
            <div class="calendar-section">
                <!-- Calendar component -->
                <Calendar/>
            </div>
        </div><!-- Calendar Full-->
    </div>
</template>

<script>
import cap from '@/assets/images/cap.png'
import job from '@/assets/images/job.png'
import time from '@/assets/images/time.png'
import help from '@/assets/images/help.png'
import energy from '@/assets/images/energy.png'
import lock from '@/assets/images/lock.png'
import wifi from '@/assets/images/wifi.png'
import washer from '@/assets/images/washer.png'
import balcony from '@/assets/images/balcony.png'
import crib from '@/assets/images/crib.png'
import kitchen from '@/assets/images/kitchen.png'
import workspace from '@/assets/images/workspace.png'
import bathtab from '@/assets/images/bathtab.png'
import dropoff from '@/assets/images/dropoff.png'
import camera from '@/assets/images/camera.png'


import Calendar from '@/components/Calendar.vue'

export default{
    name:"HostPart",
    components:{
        Calendar
    },
    data(){
        return{
            details:[
                {id:1, title: "316", subtitle: "Reviews", line:"<hr>"},
                {id:2, title: "4.86 <i class='fa-solid fa-star'></i>", subtitle: "Rating", line:"<hr>"},
                {id:3, title: "7", subtitle: "Years hosting", line:""},
            ],
            otherDetails:[
                {id:1, imgSrc: cap, title:"Where I went to school: Universidad de Psicología en Valencia"},
                {id:2, imgSrc: job, title:"My work: coach"},
                {id:3, imgSrc: time, title:"I spend too much time: Search for activities for guests" },
                {id:4, imgSrc: help, title:"For guests, I always: Help them enjoy Valencia"},
                {id:5, imgSrc: energy, title:"What makes my home unique: Good energy and feeling at home" },
            ],
            offers:[
                {id:1, imgSrc: lock, title: "Lock on bedroom door"},
                {id:2, imgSrc: kitchen, title: "Kitchen"},
                {id:3, imgSrc: wifi, title: "Wifi"},
                {id:4, imgSrc: workspace, title: "Dedicated workspace"},
                {id:5, imgSrc: washer, title: "Washer"},
                {id:6, imgSrc: bathtab, title: "Bathtub"},
                {id:7, imgSrc: balcony, title: "Private patio or balcony"},
                {id:8, imgSrc: dropoff, title: "Luggage dropoff allowed"},
                {id:9, imgSrc: crib, title: "Pack ’n play/Travel crib"},
                {id:10, imgSrc: camera, title: "Security cameras on property"},
            ],
        }
    }
}
</script>

<style>

</style>