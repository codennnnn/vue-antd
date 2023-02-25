<template>
    <div class="continer">
        <div class="continer-login">
            <img class="continer-login-icon" src="@/assets/login/login_icon.png">
            <div class="continer-login-content">
                <img src="@/assets/login/login_font.png"/>
                <div class="continer-login-content-tbas">
                    <a-tabs v-model:activeKey="activeKey" centered :tabBarStyle="{ textAlign: 'center', borderBottom: 'unset' }">
                        <a-tab-pane key="1" tab="账号密码登录"></a-tab-pane>
                        <a-tab-pane key="2" tab="手机号登录"></a-tab-pane>
                    </a-tabs>
                </div>
                <template v-if="activeKey === '1'">
                    <div class="continer-login-content-user">
                        <a-input v-model:value="userName" placeholder="请输入您的账号" class="input-class">
                            <template #prefix>
                                <img src="@/assets/login/login_user.png" class="prefix-top"/>
                            </template>
                        </a-input>
                    </div>
                    <div class="continer-login-content-pwd">
                        <a-input-password v-model:value="pwd" placeholder="请输入密码" class="input-class">
                            <template #prefix>
                                <img src="@/assets/login/login_pwd.png" class="prefix-top"/>
                            </template>
                        </a-input-password>
                    </div>
                </template>
                <template v-if="activeKey === '2'">
                    <div class="continer-login-content-user">
                        <a-input v-model:value="userName" placeholder="请输入您的账号" class="input-class"/>
                    </div>
                    <div class="continer-login-content-pwd">
                        <a-input v-model:value="pwd" placeholder="请输入密码" class="input-class">
                            <template #suffix>
                                <span style="color: rgba(38, 138, 240, 1);cursor: pointer;">获取验证码</span>
                            </template>
                        </a-input>
                    </div>
                </template>
                
                <div class="continer-login-content-forget">忘记密码？</div>
                <div class="continer-login-content-btn">登录</div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
import { ref } from 'vue';

const activeKey = ref('1')
const userName = ref('')
const pwd = ref('')
</script>

<style lang="scss" scoped>
.continer{
    height:100vh;
    width:100vw;
    overflow: hidden;
    background: url('@/assets/login/login_bg.png') no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    &-login{
        width: 1280px;
        height: 700px;
        border-radius: 10px;
        background-color: #fff;
        display: flex;
        align-items: center;
        position: relative;
        &-icon{
            width: 600px;
            height: 450px;
            position: absolute;
            left: -40px;
        }
        &-content{
            width: 550px;
            height: 570px;
            background: rgba(255, 255, 255, 1);
            border: 1px solid rgba(245, 245, 245, 1);            
            box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.1);
            position: absolute;
            right: 66px;
            text-align: center;
            img{
                width: 130px;
                height: 30px;
                position: relative;
                margin-top: 51px;

            }
            &-tbas{
                margin-top: 63px;
            }
            &-user,&-pwd{
                width: 385px;
                height: 55px;
                position: relative;
                margin: 0 auto;
                display: flex;
                align-items: center;
            }
            &-user{
                margin-top: 48px;
                img{
                    width: 15px;
                    height: 18px;
                }
            }
            &-pwd{
                margin-top: 20px;
                img{
                    width: 15px;
                    height: 17px;
                }
            }
            &-forget{
                text-decoration: underline;
                font-size: 14px;
                vertical-align: top;
                font-weight: 400;
                letter-spacing: 0.18px;
                margin-left: 320px;
                margin-top: 20px;
            }
            &-btn{
                width: 385px;
                height: 50px;
                border-radius: 5px;
                background: rgba(0, 84, 254, 1);
                text-align: center;
                color: #fff;
                font-size: 16px;
                font-weight: 600;
                letter-spacing: 0.2px;
                line-height: 50px;
                margin-top: 40px;
                position: relative;
                margin: 40px auto 0 auto;
                cursor: pointer;
            }
        }
    }
}
</style>
<style>
    .ant-tabs-nav::before{
        border-bottom: 0px !important;
    }
    .input-class{
        width: 100%;
        height:100%;
        border-radius:5px;
        display: flex;
        align-items: center;
    }
    .prefix-top{
        top: -25px;
    }
</style>