<template>
  <main>
    <div class="sticky-header" :class="{ scrolled: isScrolled }">
      <div class="container">
        <div class="row">
          <div class="col-md-6">
            <div class="header-left">
              <ul class="p-0 mb-0">
                <li class="nav-item"><a href="#gallery">Photos</a></li>
                <li class="nav-item"><a href="#amenities">Amenities</a></li>
                <li class="nav-item"><a href="#reviews">Reviews</a></li>
                <li class="nav-item"><a href="#location">Location</a></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Header />
    <MainGallery/>
    <RoomDetails/>
    <Testimonial/>
    <Map/>
    <Footer/>
  </main>
</template>

<script>
import Header from '@/components/Header.vue'
import MainGallery from '@/components/MainGallery.vue'
import RoomDetails from '@/components/RoomDetails.vue'
import Testimonial from '@/components/Testimonial.vue'
import Map from '@/components/Map.vue'
import Footer from '@/components/Footer.vue'

export default{
  name: "HomeView",
  components:{
    Header,
    MainGallery,
    RoomDetails,
    Testimonial,
    Map,
    Footer
  },
  data(){
    return{
      isScrolled: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY >= 400;
    }
  }
}
</script>


<style>
.sticky-header .header-left ul li {
    display: inline-block;
}

.sticky-header .header-left ul li a {
    display: block;
    color: var(--black);
    text-decoration: none;
    font-size: 15px;
    padding: 30px 25px 30px 0px;
    position: relative;
}
.sticky-header .header-left ul li a:hover:before {
    content: '';
    position: absolute;
    width: 65%;
    height: 3px;
    background: var(--black);
    bottom: 0;
    left: 0;
}
.sticky-header {
    border-bottom: 1px solid var(--midgray);
    display: none;
    background: #ffffff;
    z-index: 99;
    position: sticky;
    top: 0;
}
.sticky-header.scrolled {
    display: block;
}
</style>