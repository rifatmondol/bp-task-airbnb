<template>
  <div class="header">
    <nav class="navbar navbar-expand-md">
        <div class="container">
            <div class="main-logo">
                <router-link class="navbar-brand" to="/"><img src="@/assets/images/logo.png" alt="logo" class="me-1"></router-link>
            </div>
            <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar">
            <span class="navbar-toggler-icon"></span>
            </button>
            <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">
                <div class="offcanvas-header">
                    <router-link class="offcanvas-title navbar-brand" id="offcanvasNavbarLabel" to="/"><img src="@/assets/images/logo.png" alt="logo"></router-link>
                    <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
                </div>
                <div class="offcanvas-body">
                    <form class="" role="search">
                    <!-- <input class="form-control" type="button" placeholder="Start your search" aria-label="Search"> -->
                    <button class="form-control btn">Start your search</button>
                    </form>
                    <ul class="navbar-nav justify-content-end flex-grow-1">
                    <li class="nav-item">
                        <router-link class="nav-link active" aria-current="page" to="/">Airbnb your home</router-link>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#"><i class="fa-solid fa-globe"></i></a>
                    </li>
                    <li class="nav-item dropdown ms-2">
                        <a class="nav-link" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                            <i class="fa-solid fa-bars me-3"></i><i class="fa-solid fa-circle-user"></i>
                        </a>
                        <ul class="dropdown-menu">
                        <li><a class="dropdown-item" href="#">Sign up</a></li>
                        <li><a class="dropdown-item" href="#">Log in</a></li>
                        <li>
                            <hr class="dropdown-divider">
                        </li>
                        <li><a class="dropdown-item" href="#">Airbnb your home</a></li>
                        <li><a class="dropdown-item" href="#">Help</a></li>
                        </ul>
                    </li>
                    </ul>
                    
                </div>
            </div>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style>

</style>