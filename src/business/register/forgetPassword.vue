<template>
    <div class="forget-password-container">
        <l-head>
            <l-icon name="fanhui" @click.native="$router.push('/login')" slot="left-item"/>
            忘记密码
        </l-head>
        <div class="forget-password-form">
            <div class="forget-password-form-item">
                <input type="text" placeholder="手机号">
            </div>
            <div class="forget-password-form-item">
                <input type="text" placeholder="验证码" class="validate-code-input">
                <div class="btn-validate-code text-center pull-right">获取验证码</div>
            </div>
            <div class="forget-password-form-item">
                <input type="password" placeholder="新密码">
            </div>
            <div class="forget-password-form-item">
                <input type="password" placeholder="确认新密码">
            </div>
            <div class="forget-password-form-item register-btn">
                <div class="btn-register text-center" @click="submitForm">提&emsp;交</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'forget-password',
        methods: {
            submitForm() {
            
            }
        }
    }
</script>

<style lang="scss">
    .forget-password-container {
        background: url("../../../static/img/index/bg.png") no-repeat;
        width: 750px;
        height: 100%;
        padding-bottom: 0 !important;
        position: absolute;
        top: 0;
        left: 0;
        background-size: cover;
        .head-title {
            background-color: transparent;
        }
        .forget-password-form {
            width: 580px;
            margin: 80px auto 0;
            .forget-password-form-item {
                margin-bottom: 40px;
                input {
                    font-size: 28px;
                    line-height: 28px;
                    padding: 35px 10px 35px 30px;
                    width: 580px;
                    background-color: rgba(255, 255, 255, 0.1);
                    -webkit-border-radius: 8px;
                    -moz-border-radius: 8px;
                    border-radius: 8px;
                    color: #ffffff;
                    &.validate-code-input {
                        width: 360px;
                    }
                }
                input::-webkit-input-placeholder {
                    color: #999999;
                }
                input:-moz-placeholder {
                    color: #999999;
                }
                input::-moz-placeholder {
                    color: #999999;
                }
                input:-ms-input-placeholder {
                    color: #999999;
                }
                .btn-validate-code {
                    width: 188px;
                    font-size: 28px;
                    line-height: 28px;
                    border: 2px solid #F8C513;
                    -webkit-border-radius: 8px;
                    -moz-border-radius: 8px;
                    border-radius: 8px;
                    color: #F8C513;
                    padding: 35px 0;
                }
                &.register-btn {
                    margin-top: 353px;
                    .btn-register {
                        width: 580px;
                        font-size: 34px;
                        line-height: 34px;
                        background-color: #F8C513;
                        -webkit-border-radius: 8px;
                        -moz-border-radius: 8px;
                        border-radius: 8px;
                        color: #25252B;
                        padding: 32px 0;
                    }
                }
            }
        }
    }
</style>
