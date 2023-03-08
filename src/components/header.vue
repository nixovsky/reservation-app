<template>
    <div 
        @click="closeAll"
        class="modal-backgrop"
    ></div>
    <profile-settings
        v-if="activeSettings"
        @closeProfileSettings="activeSettings = false"
    ></profile-settings>
    <header class="header">
        <h1 class="logo">Reservation</h1>
        <div class="search">
            <form action="">
                <input class="search__space" type="search" placeholder="Поиск">
            </form>
        </div>
        <nav>
            <div class="home__btn nav__btn">
                <button><img src="../assets/icon/home.svg" alt=""></button>
            </div>
            <div @click="showCatalog" class="catalog__btn nav__btn">
                <button><img src="../assets/icon/menu.svg" alt=""></button>
            </div>
            <transition name="fade">
                <div v-show="activeCatalog" class="drop-box catalog">
                    <ul>
                        <li><a href="#">Квартиры</a></li>
                        <li><a href="#">Офисы</a></li>
                        <li><a href="#">Склады</a></li>
                        <li><a href="#">Торговые помещения</a></li>
                        <li><a href="#">Производственные помещения</a></li>
                    </ul>
                </div>
            </transition>
        </nav>
        <div class="profile-wrapper">
            <div @click="showProfileMenu" class="profile">
                <img src="../assets/image/profile-image.png" alt="" class="profile__img">
                <h3 class="profile__name">Никита Крикунов</h3>
            </div>
            <transition name="fade">
                <div v-show="activeProfile" class="drop-box profile__info">
                    <ul>
                        <li 
                            @click="activeSettings = true"
                        ><a href="#">Настройки</a></li>
                        <li><a href="#">Выход</a></li>
                    </ul>
                </div>
            </transition>
        </div>
    </header>

</template>

<script>
import profileSettings from './profileSettings.vue'

export default {
    data(){
        return{
            activeCatalog: false,
            activeProfile: false,
            activeSettings: false,
        }
    },
    methods: {
        showCatalog(event){
            console.log(event)
            this.activeCatalog = !this.activeCatalog;
            this.activeProfile = false;
        },
        showProfileMenu(){
            this.activeProfile = !this.activeProfile;
            this.activeCatalog = false;
        },
        closeAll(){
            this.activeProfile = false;
            this.activeCatalog = false
        }
    },
    components: {
        profileSettings
    }
}
</script>