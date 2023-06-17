<template>
    <div class="testimonial" id="reviews">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <div class="testimonial-top mb-5">
                        <div class="review">
                            <h4><i class="fa-solid fa-star"></i> <span>4.87<span> . </span></span>171 reviews</h4>
                        </div>
                        <div class="behaviour mt-4">
                            <div class="row">
                                <div class="col-sm-6" v-for="behaviour in behaviours" :key="behaviour.key">
                                    <div class="behaviour-item">
                                        <div class="item-title">
                                            <p class="mb-0">{{ behaviour.title }}</p>
                                        </div>
                                        <div class="item-rating">
                                            <div class="rating-bar"></div>
                                            <div class="rating">
                                                <p class="mb-0">{{ behaviour.rating }}</p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                
                            </div>
                        </div>
                    </div>
                    <div class="testimonial-bottom">
                        <div class="row">
                            <div class="col-sm-6" v-for="avatarDetail in avatarDetails" :key="avatarDetail.id">
                                <div class="left-item">
                                    <div class="avatar">
                                        <img :src="avatarDetail.imgSrc" alt="image">
                                        <div class="avatar-details">
                                            <h6 class="mb-0">{{ avatarDetail.title }}</h6>
                                            <span>{{ avatarDetail.date }}</span>
                                        </div>
                                    </div>
                                    <p class="mt-3 mb-2">{{ avatarDetail.description }}</p>
                                    <a href="#" v-html="avatarDetail.show"></a>
                                </div>
                            </div>
                        </div>
                    </div>
                    <button class="offer-btn mt-md-3">Show all 171 reviews</button>
                    <div class="hrline my-md-5 my-4"><hr></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import avatar1 from '@/assets/images/avatar-1.webp'
import avatar2 from '@/assets/images/avatar-2.webp'
import avatar3 from '@/assets/images/avatar-3.webp'
import avatar4 from '@/assets/images/avatar-4.webp'
import avatar5 from '@/assets/images/avatar-5.webp'
import avatar6 from '@/assets/images/avatar-6.webp'

export default{
    name:"Testimonial",
    data(){
        return{
            behaviours: [
                {id:1, title:"Cleanliness", rating: "4.9"},
                {id:2, title:"Accuracy", rating: "4.9"},
                {id:3, title:"Communication", rating: "5.0"},
                {id:4, title:"Location", rating: "5.0"},
                {id:5, title:"Check-in", rating: "5.0"},
                {id:6, title:"Value", rating: "4.8"},
            ],

            avatarDetails: [
                {id:1, imgSrc: avatar1, title:"Natasha", date: "May 2023", description: "Great location and a wonderful host, couldn't ask for more", show: ""},
                {id:2, imgSrc: avatar2, title:"Martin", date: "May 2023", description: "I had a Great Time Staying at Sagrario’s place! Her apartment is perfectly located in the centre of el Carmen. Her information on festivities and the area were one of a kind. I can only", show: "Show more <i class='fa-solid fa-angle-right'></i>"},
                {id:3, imgSrc: avatar3, title:"Saskia", date: "May 2023", description: "Sagrario is a superhost! She is very kind, helpful and friendly. She gives you advice about activities in Valencia.The apartment is great, clean and in the middle of the historic center. I loved", show: "Show more <i class='fa-solid fa-angle-right'></i>"},
                {id:4, imgSrc: avatar4, title:"Merel", date: "March 2023", description: "I loved staying with Sagrario. She is an incredible host. She’s friendly, always responds quickly and she made me feel at home. She gave me more than enough recommendations for", show: "Show more <i class='fa-solid fa-angle-right'></i>"},
                {id:5, imgSrc: avatar5, title:"Clara", date: "March 2023", description: "She was really kind. Gracias Sagrario!", show: ""},
                {id:6, imgSrc: avatar6, title:"Sean", date: "February  2023", description: "Best bnb host! Very helpful whenever you need recommendations, very welcoming and makes you feel at home. Everything was perfect!"},
            ],
        }
    }
}
</script>

<style>

</style>