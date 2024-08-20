<template>  
    <view class="tiele_box">    
        <image class="return" src="../../static/chat/返回键.png" @click="toMessage()"></image>  
        <view class="name_box">  
            <text class="name">金贵妃</text>  
        </view>  
        <image class="my" src="../../static/icon1/我的.png" @click="toMy()"></image>  
    </view>  
    <div>  
        <div class="chat-container" ref="chatContainer">   
            <div v-for="(message, index) in messages" class="message-container" :key="index">  
                <div class="avatar-container" :class="{ 'user-avatar': message.user, 'other-avatar': !message.user }">  
                    <img v-if="message.user" class="avatar1" src="../../static/chat/我.png" @click="toMessage()">  
                    <img v-else class="avatar2" src="../../static/chat/他.png" @click="toMessage()">  
                </div>  
                <div class="message" :class="{ user: message.user, other: !message.user }">  
                    <span v-html="formatMessage(message.text)"></span>  
                </div>  
            </div>  
        </div>  

        <div class="input-container">  
            <textarea v-model="newMessage" @input="handleInput(event)" placeholder="Type your message..." rows="1" @focus="autoGrow()" @keypress.enter.prevent="sendMessage()"></textarea>  
            <button @click="sendMessage()">发送</button>  
        </div>  
    </div>  
</template>  

<script>  
export default {  
    data() {  
        return {  
            newMessage: '',  
            messages: [  
                { text: "Hello! How are you?", user: true },  
                { text: "I'm good, thank you! How about you?", user: false },  
                { text: "I'm doing well, thanks for asking!", user: true }  
            ]  
        };  
    },  
    methods: {  
        sendMessage() {  
            if (this.newMessage.trim()) {   
                this.messages.push({ text: this.newMessage, user: true });  
                this.newMessage = '';  
                this.scrollToBottom();  
            }  
        },   
        formatMessage(text) {  
            // 使用 replace 保留换行符和空格  
            return text.replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/\n/g, "<br/>").replace(/ /g, "&nbsp;");  
        },  
        scrollToBottom() {  
            this.$nextTick(() => {  
                const container = this.$refs.chatContainer;  
                container.scrollTop = container.scrollHeight;  
            });  
        },  
        updateMessage(event) {  
            this.newMessage = event.target.value;  
        },   
        autoGrow(event) {  
            const textarea = event.target;  
            textarea.style.height = "auto";  
            textarea.style.height = (textarea.scrollHeight) + "px";  
        },  
        handleInput(event) {  
            this.updateMessage(event);  
            this.autoGrow(event);  
        },  
        toMessage() {  
            uni.switchTab({  
                url: "/pages/message/message"  
            })  
        },  
        toMy() {  
            uni.switchTab({  
                url: "/pages/my/my"  
            })  
        }  
    }  
}  
</script>  

<style>  
.tiele_box {  
    height: 90rpx;  
    width: 100%;  
    background-color: #F8F8F8;  
    margin-left: 5%;  
    margin-top: 0rpx;  
}  
.return {  
    height: 40%;  
    width: 5%;  
    float: left;  
    margin-right: 5%;  
    margin-top: 30rpx;  
}  
.name_box {  
    height: 40%;  
    width: 40%;  
    float: left;  
    margin-right: 5%;  
    margin-top: 22rpx;  
}  
.name {  
    font-size: 15px;  
}  
.my {  
    height: 70%;  
    width: 8%;  
    float: right;  
    margin-right: 10%;  
    margin-top: 10rpx;  
}  
.chat-container {  
    height: 560px;  
    width: 380px;  
    background-color: #f1f1f1;  
    padding: 10px;  
    overflow-y: auto;  
    display: flex;  
    flex-direction: column;  
    align-items: flex-start;  
}  

.message-container {  
    display: flex;  
    align-items: flex-start;  
    margin: 5px 0;   
}  

.message {  
    padding: 10px;  
    border-radius: 10px;  
    max-width: 300px;  
    word-wrap: break-word;  
}  

.message.user {  
    background-color: #007bff;  
    color: white;   
    align-self: flex-end;  
}  

.message.other {  
    background-color: #e1e1e1;  
    align-self: flex-start;  
}  

.avatar1,  
.avatar2 {  
    height: 20px;  
    width: 20px;  
    margin-right: 10px;  
}  

.input-container {  
    display: flex;  
    border-top: 1px solid #ccc;  
    width: 100%;  
    height: 35px;  
    background-color: #fff;  
}  

.input-container textarea {  
    flex: 1;  
    height: auto;  
    border: 1px solid #ccc;  
    border-radius: 5px;  
    margin-right: 5px;  
    margin-left: 5px;  
    margin-top: 1%;  
    resize: none;   
    overflow: hidden;  
    font-size: 40rpx;  
}  

.input-container button {  
    width: 20%;  
    height: 100%;  
    border: none;  
    border-radius: 5px;  
    background-color: #007bff;  
    font-size: 30rpx;  
    color: #ffffff;  
    margin-top: 1%;  
    margin-right: 1%;  
    cursor: pointer;  
}  

.input-container button:hover {  
    background-color: #0069d3;  
}  
</style> 