<template>
    <div class="main-gallery" id="gallery">
        <div class="photo-gallery mt-3">
            <div class="container">
                <div class="main-image-header">
                    <div class="row">
                        <div class="col-md-6">
                            <div class="image-top">
                            <h3>Enjoy historic Valencia and close to the beach.</h3>
                            <p>
                                <span class="me-2 d-inline-block"><i class="fa-solid fa-star"></i> <span>4.87</span> . <a href="#">171 reviews</a></span> 
                                <span>.  <img src="@/assets/images/dot.png" alt="dot">  <span>Superhost</span> . <a href="#">Valencia, Spain</a></span>
                            </p>
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="image-top">
                            <p class="image-share text-end">
                                <span class="me-2 d-inline-block"><i class="fa-solid fa-arrow-up-from-bracket"></i><a href="#" class="ms-2"> Share</a></span>
                                <span class="ms-2"><i class="fa-regular fa-heart"></i><a href="#" class="ms-2"> Save</a></span>
                            </p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="main-image mt-md-2">
                    <div class="row">
                        <div class="col-md-6 image-col">
                            <div class="image-item">
                                <img src="@/assets/images/top-photo-1.webp" alt="top-1">
                            </div>
                        </div>
                        <div class="col-md-6 image-col">
                            <div class="row">
                                <div class="col-md-6 image-col2" v-for="mainphoto in mainphotos1" :key="mainphoto.id">
                                    <div class="image-item">
                                        <img :src="mainphoto.topPhoto" alt="top-2">
                                    </div>
                                </div>
                            </div>
                            <div class="row mt-md-2">
                                <div class="col-md-6 image-col2" v-for="mainphoto in mainphotos2" :key="mainphoto.id">
                                    <div class="image-item">
                                        <img :src="mainphoto.topPhoto" alt="top-2">
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
import topPhoto2 from '@/assets/images/top-photo-2.webp'
import topPhoto3 from '@/assets/images/top-photo-3.webp'
import topPhoto4 from '@/assets/images/top-photo-4.webp'
import topPhoto5 from '@/assets/images/top-photo-5.webp'

export default{
    name:"MainGallery",
    data(){
    return{
      mainphotos1:[
        {id:1, topPhoto : topPhoto2},
        {id:2, topPhoto : topPhoto3}
      ],
      mainphotos2:[
        {id:3, topPhoto : topPhoto4},
        {id:4, topPhoto : topPhoto5},
      ],

    }
  }
}
</script>

<style>

</style>