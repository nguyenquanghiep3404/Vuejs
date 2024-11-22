<template>
    <div>
        <h3>Form Binding</h3>

    </div>
    <div>
        <form action="">
            <!-- text -->
            <div class="form-group">
                <label for="email">Email</label>
                <input class="form-control" type="text" v-model="email">
            </div>
        </form>
        <!-- multi text -->
        <div>
            <label for="contact" >Contact</label>
            <textarea name="contact" id="contact" cols="30" rows="10" v-model="contact" placeholder="please enter contatc"></textarea>
        </div>
        <!-- checkbox -->
        <div class="form-group">
                <label for="email">clause</label>
                <input  type="checkbox" v-model="isChecked" >
            </div>
        <!-- multi check -->
        <div class="form-group">
                <h3>Gender</h3>
                <label for="">male</label>
                <input  type="checkbox" v-model="gender" value="male" >
                <label for="">female</label>
                <input type="checkbox" v-model="gender" value="female">
        </div>
        <label for="language">Chọn ngôn ngữ lập trình: </label>
            <select id="language"v-model="selectedLanguage">
            <option value="JavaScript">JavaScript</option>
            <option value="Java">Java</option>
            <option value="C++">C++</option>
        </select>
        <p>Ngôn ngữ lập trình bạn chọn là: {{selectedLanguage}}</p>
        <p>{{email}}</p>
        <p>{{ contact }}</p>
        <p>{{ isChecked }}</p>
        <p>{{ gender }}</p>

        <div>
            <div>Màu bạn chọn: {{favoriteColor}}</div>
            <input type="radio"id="red" value="Red" v-model="favoriteColor"/>
            <label for="red">Đỏ</label>
            <input type="radio"id="green" value="Green" v-model="favoriteColor"/>
            <label for="green">Xanh lá</label>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';


    const email = ref("");
    const contact = ref("NQH");
    const isChecked = ref(false);
    const gender = ref ([]);
    const selectedLanguage = ref("JavaScript");
    const favoriteColor = ref("Red");
</script>

<style lang="scss" scoped>

</style>