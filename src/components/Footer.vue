<template>
    <div class="footer">
        <div class="footer-things mb-md-5 mb-3">
            <div class="container">
                <div class="row">
                    <div class="col-md-12">
                        <h4 class="mb-4">Things to know</h4>
                        <div class="row">
                            <div class="col-md-4 col-sm-6" v-for="thing in things" :key="thing.id">
                                <div class="things-item">
                                    <h6>{{ thing.title }}</h6>
                                    <ul class="thing-list">
                                        <li v-for="list in thing.lists" :key="list.key">{{ list.listtitle }}</li>
                                    </ul>
                                    <a href="#" v-html="thing.button"></a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="main-footer">
            <div class="footer-top py-md-5 py-3">
                <div class="container">
                    <div class="row">
                        <div class="col-md-12">
                            <h4 class="mb-4">Explore other options in and around Valencia</h4>
                            <div class="row">
                                <div class="col-sm-3 col-4" v-for="(location, index) in locations" :key="index">
                                    <div class="location">
                                        <a href="#">{{ location }}</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-12 mt-md-5 mt-4">
                            <h6 class="mb-md-4 mb-3">Other types of stays on Airbnb</h6>
                            <div class="row">
                                <div class="col-lg-3 col-md-4 col-sm-6" v-for="(location, index) in otherLocations" :key="index">
                                    <div class="location">
                                        <a href="#">{{ location }}</a>
                                    </div>
                                </div>
                                <div class="col-md-12">
                                    <div class="hamburg-local mt-4">
                                        <a href="#" class="me-2" v-for="(hamburgLocal, index) in hamburgLocals" :key="index">{{ hamburgLocal }} <i class="fa-solid fa-angle-right ms-1"></i></a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="footer-middle py-md-5 py-3">
                <div class="container">
                    <div class="row">
                        <div class="col-md-3 col-sm-6" v-for="thing in Footerthings" :key="thing.id">
                            <div class="footer-middle-item">
                                <h6>{{ thing.title }}</h6>
                                <ul class="footer-middle-list mb-0">
                                    <li v-for="list in thing.lists" :key="list.key"><a href="#">{{ list.listtitle }}</a></li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <div class="container">
                    <div class="row">
                        <div class="col-md-12">
                            <div class="footer-bottom-main py-4">
                                <div class="row">
                                    <div class="col-md-6">
                                        <div class="footer-bottom-item">
                                            <span>© 2023 Airbnb, Inc. - </span>
                                            <span><a href="#">Terms</a> . </span>
                                            <span><a href="#">Sitemap</a> . </span>
                                            <span><a href="#">Privacy</a> . </span>
                                            <span><a href="#">Your Privacy Choices</a></span>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <div class="footer-bottom-item text-md-end">
                                            <span><a href="#"><i class="fa-solid fa-globe"></i></a></span>
                                            <span><a href="#">English (US)</a></span>
                                            <span><a href="#">$ USD</a></span>
                                            <span><a href="#"><i class="fa-brands fa-square-facebook"></i></a></span>
                                            <span><a href="#"><i class="fa-brands fa-square-twitter"></i></a></span>
                                            <span><a href="#"><i class="fa-brands fa-square-instagram"></i></a></span>
                                        </div>
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
export default{
    name:"Footer",
    data(){
        return{
            things:[
                {
                    id:1, 
                    title: "House rules", 
                    lists:[
                        {id:1, listtitle: "Check-in after 2:00 PM"},
                        {id:2, listtitle: "Checkout before 11:00 AM"},
                        {id:3, listtitle: "2 guests maximum"},
                    ],
                    button:"Show more <i class='fa-solid fa-angle-right'></i>"
                },
                {
                    id:2, 
                    title: "Safety & property", 
                    lists:[
                        {id:1, listtitle: "Security camera/recording device"},
                        {id:2, listtitle: "Carbon monoxide alarm"},
                        {id:3, listtitle: "Smoke alarm"},
                    ],
                    button:"Show more <i class='fa-solid fa-angle-right'></i>"
                },
                {
                    id:3, 
                    title: "Cancellation policy", 
                    lists:[
                        {id:1, listtitle: "Add your trip dates to get the cancellation details for this stay."},
                    ],
                    button:"Add dates <i class='fa-solid fa-angle-right'></i>"
                },
            ],
            locations:["Dénia","Calp","Benidorm","Alicante","Ibiza","Torrevieja","Formentera","Salou","Tarragona","Palma","Sitges","Majorca"],

            otherLocations:["Valencia vacation rentals","Valencia monthly stays","Apartment rentals in Valencia","Apartment rentals in Spain","Luxury rentals in Spain"],

            hamburgLocals:["Airbnb","Spain","Valencian Community","Valencia Region","Valencia"],

            Footerthings:[
                {
                    id:1, 
                    title: "Support", 
                    lists:[
                        {id:1, listtitle: "Help Center"},
                        {id:2, listtitle: "AirCover"},
                        {id:3, listtitle: "Supporting people with disabilities"},
                        {id:4, listtitle: "Cancellation options"},
                        {id:5, listtitle: "Our COVID-19 Response"},
                        {id:6, listtitle: "Report a neighborhood concern"},
                    ],
                },
                {
                    id:2, 
                    title: "Community", 
                    lists:[
                        {id:1, listtitle: "Airbnb.org: disaster relief housing"},
                        {id:2, listtitle: "Combating discrimination"}
                    ],
                },
                {
                    id:3, 
                    title: "Hosting", 
                    lists:[
                        {id:1, listtitle: "Airbnb your home"},
                        {id:2, listtitle: "AirCover for Hosts"},
                        {id:3, listtitle: "Explore hosting resources"},
                        {id:4, listtitle: "Visit our community forum"},
                        {id:5, listtitle: "How to host responsibly"},
                        {id:6, listtitle: "Airbnb-friendly apartments"},
                    ],
                },
                {
                    id:4, 
                    title: "Airbnb", 
                    lists:[
                        {id:1, listtitle: "Newsroom"},
                        {id:2, listtitle: "Learn about new features"},
                        {id:3, listtitle: "Letter from our founders"},
                        {id:4, listtitle: "Careers"},
                        {id:5, listtitle: "Investors"},
                        {id:6, listtitle: "Gift cards"},
                    ],
                },
            ]
        }
    }
}
</script>