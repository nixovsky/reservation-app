<template>
    <div class="profile-settings__wrapper">
        <div class="profile-settings">
            <h3 class="profile-settings__title">Настройки профиля</h3>
            <form action="">
                <div class="profile-settings__element profile-settings__name">
                    <label for="name">Имя</label>
                    <input type="text" name="name">
                </div>
                <div class="profile-settings__element profile-settings__surname">
                    <label for="surname">Фамилия</label>
                    <input type="text" name="surname" id="surname">
                </div>
                <div class="profile-settings__element profile-settings__phone">
                    <label for="phone">Номер телефона</label>
                    <input type="tel" name="phone" id="phone" placeholder="+7 000 000-00-00">
                </div>
                <div class="profile-settings__element profile-settings__email">
                    <label for="mail">Почта</label>
                    <input type="email" name="mail" id="email">
                </div>
                <div class="profile-setting__buttons">
                    <button class="profile-settings__submit profile-settings__btn" type="submit">Сохранить</button>
                    <button class="profile-settings__cancel profile-settings__btn" @click="$emit('closeProfileSettings')">Отмена</button>
                </div>
            </form>
        </div>
    </div>   
</template>

<script>
export default {
    emits: ['closeProfileSettings'],
    data () {
        return{

        }
    }
}
</script>