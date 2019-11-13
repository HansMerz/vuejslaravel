<template>
    <div>
        <header>
            <div class="collapse bg-dark" id="navbarHeader">
                <div class="container">
                    <div class="row">
                        <div class="col-sm-8 col-md-7 py-4">
                        <h4 class="text-white">SPA y Componentes</h4>
                        <p class="text-muted">Curso</p>
                        </div>
                        <div class="col-sm-4 offset-md-1 py-4">
                        <h4 class="text-white">Navegación</h4>
                        <ul class="list-unstyled">
                            <li>
                                <router-link :to="{name: 'home'}">Home</router-link>
                            </li>
                            <li>
                                <router-link :to="{name: 'blog'}">Blog</router-link>
                            </li>                            
                        </ul>
                        </div>
                    </div>
                </div>
            </div>
            <div class="navbar navbar-dark bg-dark box-shadow">
                <div class="container d-flex justify-content-between">
                <router-link :to="{name: 'home'}" href="#" class="navbar-brand d-flex align-items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mr-2"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"></path><circle cx="12" cy="13" r="4"></circle></svg>
                    <strong>Curso VUE LARAVEL</strong>
                </router-link>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarHeader" aria-controls="navbarHeader" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                </div>
            </div>
        </header>

        <transition name="slide-fade" mode="out-in">
            <router-view :key="$route.fullPath"></router-view>
        </transition>                
    </div>
</template>