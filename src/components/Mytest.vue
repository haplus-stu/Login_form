<template>
    <div class="pg-wrapper">
        <div id="form">
            <h2 id="title">{{title}}</h2>
            <div class="form_fact">
                <p class="formlabel">メールアドレス</p>
                <input type="email" id="adress">
            </div>
            <br>
            <div class="form_fact" id="password_form">
                <p class="formlabel">パスワード</p>
                <input type="password" id="pass">
                <br>
                <span id="view_password" @click="onClick">パスワードを表示</span>
            </div>
            <button type="submit" id="login">ログイン</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Mytest',
        props: {
            title: String
        },
        methods:{
            onClick: function(e){
                let pass_form = document.getElementById('pass');
                let text = document.getElementById('view_password');

                if(pass_form.hasAttribute("type","text") == true){
                    pass_form.removeAttribute("type","text");
                    text.textContent='パスワードを非表示';
                }else if(pass_form.hasAttribute("type","text") != true){
                    pass_form.setAttribute("type","password");
                    text.textContent='パスワードを表示';
                }
                this.$emit('click',e);
                
            }
        },
    }

</script>

<style lang="scss">

    #form {
        width: 330px;
        margin: 20vh auto 0 auto;
        border: 1px solid #dbdbdb;
        padding: 100px 60px 80px 60px;
        border-radius: 2px;
    #title{
        margin-bottom: 5vh;
    }

    input {
        width: 250px;
        height: 50px;
        border-radius: 3px;
        border: 1px solid #c7c7c7;
        margin-bottom: 1.75vh;

        &:focus {
            border: 2px solid #287AE6;
        }
    }
    .form_fact {
        position: relative;
        display: block;

    }
    .formlabel {
        position: absolute;
        top: -22px !important;
        font-size: 14px;
        left: 28px;
        background-color: #fff;
    }

    #view_password{
        color:#287AE6;
        margin-left: 15px;
        &:hover{
            cursor: pointer;
        }
    }
    
    #login {
        width: 250px;
        height: 50px;
        border-radius: 3px;
        border: 1px solid #c7c7c7;
        background-color: #287AE6;
        color: #f4f6f7;
        outline: 0;
        // FireFox
        &::-moz-focus-inner {
            border-style: none;
        }

        &:hover {
            cursor: pointer;
        }
    }
    }



</style>