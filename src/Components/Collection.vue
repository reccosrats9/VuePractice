<template>
    <div id='outer'>
        <div>
            <h2>Bot 1:</h2>
            <h2>Bot 2:</h2>
        </div>
        <div id='collection'>
        <div v-for="bot in bots" :key='bot.id' id='botBox'>
                <h1>{{bot.botName}}</h1>
                <div id='botInfo'>
                    <div>
                        <h1>Attack: {{bot.attack}}</h1>
                        <h1>Health: {{bot.health}}</h1>
                    </div>
                    <img :src="bot.img" alt="">
                </div>
                <div id='buttons'>
                    <h3>SELECT</h3>
                    <h3>RETIRE</h3>
                </div>
        </div>
        </div>
    </div>
</template>

<script>
import Bot from './Bot'

export default {
    props: ['bots'],
    components:{
        bot: Bot
    },
    data(){
        return{
            selected:[]
        }
    },
    // method: 

}
</script>

 <style scoped>
 #outer{
     display:flex;
     flex-direction: column;
 }
 #collection{
     display: flex;
     justify-content: space-around;
     flex-wrap: wrap;
 }
#botBox{
    height: 260px;
    width: 300px;
    background: whitesmoke;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    margin: 20px;
}
#botInfo{
    display: flex;
    justify-content: space-around
}
#buttons{
    display: flex;
    justify-content: space-around;
}
img{
    max-height: 100px;
    border-radius: 10px;
}
h3{
    background: gray;
    color: whitesmoke;
    padding: 4px;
    border-radius: 5px;
}
 </style>