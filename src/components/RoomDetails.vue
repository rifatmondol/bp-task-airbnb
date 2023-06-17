<template>
    <div class="room-details mt-md-5">
        <div class="room-header">
            <div class="container">
                <div class="row">
                    <div class="col-md-7">
                        <div class="row">
                            <div class="col-lg-10 col-9">
                                <div class="room-header-item">
                                    <h4 class="mb-0">Room in a rental unit hosted by Sagrario</h4>
                                </div>
                            </div>
                            <div class="col-lg-2 col-3">
                                <div class="room-header-item text-end">
                                    <img src="@/assets/images/host-photo.webp" alt="host">
                                </div>
                            </div>
                        </div>
                        <div class="room-body mt-3">
                            <div class="row">
                                <div class="col-lg-4 col-md-6 col-sm-4" v-for="item in items" :key="item.id">
                                    <div class="room-body-item">
                                        <span class="me-3 d-inline-block"><img :src="item.imgSrc" alt="image"></span>
                                        <span class="title">{{ item.title }}</span>
                                    </div>
                                </div>
                            </div>
                            <div class="hrline my-4"><hr></div>
                            <div class="unit-section">
                                <div class="row">
                                    <div class="col-md-12" v-for="unit in units" :key="unit.key">
                                        <div class="unit-item">
                                            <span class="me-3"><img :src="unit.imgSrc" alt="unit image"></span>
                                            <div class="unit-text">
                                                <h5 class="mb-2">{{ unit.title }}</h5>
                                                <span class="d-block">{{ unit.subtitle }}</span>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="hrline my-4"><hr></div>
                            <div class="translate">
                                <span> <i class="fa-solid fa-language"></i><span class="ms-2">Some info has been automatically translated. </span><a href="#">Show original language</a></span>
                            </div>
                            <div class="hrline my-4"><hr></div>
                        </div>

                        <div class="meet-host">
                            <HostPart/>
                        </div>
                    </div> 


                    <div class="col-md-5">
                        <div class="availability-main">
                            <div class="avability-section">
                                <h4>Add dates for prices</h4>
                                <span class="me-2 d-inline-block"><i class="fa-solid fa-star"></i> <span>4.87</span> . <a href="#">171 reviews</a></span>
                                <div class="date mt-4">
                                    <div class="checking">
                                        <div class="check-in">
                                            <p class="mb-0">CHECK-IN</p>
                                            <input type="text" placeholder="Add date">
                                        </div>
                                        <div class="check-out">
                                            <p class="mb-0">CHECK-OUT</p>
                                            <input type="text" placeholder="Add date">
                                        </div>
                                    </div>
                                    <div class="guest">
                                        <div class="dropdown">
                                            <a class="nav-link dropdown-toggle" href="#" @click.prevent.stop="showDropdown">
                                                <p class="mb-0">GUESTS</p>
                                                <span>1 guest</span>
                                            </a>
                                            <div class="dropdown-menu" :class="{'show': dropShow}" @click.stop>                                           
                                                <div class="guest-details" v-for="guest in guests" :key="guest.id">
                                                    <div class="guest-type">
                                                        <h6 class="mb-1">{{guest.title}}</h6>
                                                        <p class="mb-0">{{guest.subtitle}}</p>
                                                    </div>
                                                    <div class="guest-quantity">
                                                        <button @click.prevent.stop="guest.value--">-</button>
                                                        <span>{{guest.value}}</span>
                                                        <button @click.prevent.stop="guest.value++">+</button>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                
                                <button class="availability-btn mt-3">Check availability</button> 
                                
                            </div>
                            <span class="report d-block mt-4 text-center"><i class="fa-solid fa-flag me-3"></i> <a href="#">Report this listing</a></span>
                        </div>
                    </div>

                    <div class="hrline my-4"><hr></div>
                </div>
            </div>
        </div>
        <!-- <div class="room-body mt-3">
            <div class="container">
                <div class="row">
                    <div class="col-md-7">
                        
                    </div>
                </div>
            </div>
        </div> -->
    </div>
</template>

<script>
import bed from '@/assets/images/bed.png'
import shower from '@/assets/images/shower.png'
import home from '@/assets/images/home.png'
import rental from '@/assets/images/rental.png'
import dedicated from '@/assets/images/dedicated.png'
import sargario from '@/assets/images/sargario.png'

import HostPart from "@/components/HostPart.vue"

export default{
    name: "RoomDetails",
    components:{
        HostPart
    },
    data(){
        return{
            items:[
                {id: 1, imgSrc: bed, title: "1 double bed"},
                {id: 2, imgSrc: shower, title: "Shared bathroom"},
                {id: 3, imgSrc: home, title: "Host and other guests may be here"},
            ],
            units:[
                {id: 1, imgSrc: rental, title: "Room in a rental unit", subtitle: "Your own room in a home, plus access to shared spaces."},
                {id: 2, imgSrc: dedicated, title: "Dedicated workspace", subtitle: "A room with wifi that’s well-suited for working."},
                {id: 3, imgSrc: sargario, title: "Sagrario is a Superhost", subtitle: "Superhosts are experienced, highly rated hosts who are committed to providing great stays for guests."},
            ],
            guests:[
                {id:1, title: "Adults", subtitle:"Age 13+", value:1},
                {id:1, title: "Children", subtitle:"Ages 2–12", value:0},
                {id:1, title: "Infants", subtitle:"Under 2", value:0},
                {id:1, title: "Pets", subtitle:"Bringing a service animal?", value:0},
            ],
            dropShow: false
            
        }
    },
    methods:{
        showDropdown(){
            this.dropShow = !this.dropShow
        },
        handleClick(){
            this.dropShow = false
        }
    },
    mounted(){
        window.addEventListener('click', this.handleClick);
    }
}
</script>

<style>

</style>