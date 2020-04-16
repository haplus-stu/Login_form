<template>
    <div class="pg-wrapper">
        <div id="form">
            <h2 id="title">{{title}}</h2>
            <div class="form_fact">
                <p class="formlabel">メールアドレス</p>
                <input type="email" id="adress">
            </div>
            <br>
            <div class="form_fact">
                <p class="formlabel">パスワード</p>
                <input type="password" id="pass">
                    <input type="checkbox" name="" id="disp_password" v-on:click="onClick" +>
            </div>
            <button type="submit" id="login">ログイン</button>
        </div>
    </div>
</template>
<script>
export default {
    name:'my-test',
    props:{
        title: String
    },
}
</script>