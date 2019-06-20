<template>
  <div class='chat'>
  <div class='user'>
        <span>Ваше имя:</span>
        <input v-model='userIn' type = 'text' placeholder = 'Введите имя'/>
    </div>
  <div class='list-wrap'>
    <ul class='list wrap'>
        <li v-for='data in this.messages'>
            <span class='msg-user-name'>{{data.name}}</span> <span class='msg-user-time'> ({{data.date}}) </span>: <span>{{data.text}}</span>
        </li>
    </ul>
    <div class='input-wrap'>
        <input v-model='messageIn' type = 'text' placeholder = 'Введите сообщение'/>
        <button v-on:click = 'pushMessage' name='submit'>Отправить</button>
    </div>
    </div>

    <div class='user-list wrap'>
        <ul>
            <li v-for='user in this.users'>{{user}}</li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            messageIn: '',
            messages: [],
            userIn: '',
            users: []
        }
    },
    methods: {
        pushMessage(){
            let date = new Date();
            let data = {
                'name': this.userIn,
                'date': date.getHours() + ':' + date.getMinutes(),
                'text': this.messageIn
            };
            this.messages.push(data)
            this.messageIn = '';

            if(this.users.indexOf(this.userIn) == -1){
              this.users.push(this.userIn)
            }
        }
    }
}
</script>

<style>
    ul{
       list-style: none;
       padding-right: 0
    }
    .wrap{
        border: 1px solid #000;
        padding: 10px;
        position: relative;
        overflow-y: auto;
    }
    .user span{
        margin-right: 10px
    }
    .chat{
        position: absolute;
        right: 20px;
        bottom: 20px;
    }
    .list-wrap{
        float: left;
    }
    .list{
        width: 600px;
        height: 200px;
        margin-right: 10px;
    }
    .list li{
        width: 40%;
        padding: 5px 15px;
        margin-bottom: 5px;
        background-color: #f0f0f0;
        border: 1px solid #A7A7A7;
        border-radius: 5px;
        box-shadow: 0 2px 5px rgba(167, 167, 167, 0.8);
    }
    .msg-user-name{
        color: red
    }
    .msg-user-time{
        color: grey;
        font-size: 80%
    }
    .input-wrap{
        margin-top: 10px;
    }
    .input-wrap input{
        width: 70%;
        margin-right: 10px;
    }
    .input-wrap button{
        width: calc(30% - 20px);
    }
    .user-list{
        margin-top: 16px;
        width: 200px;
        height: 200px;
    }
</style>
