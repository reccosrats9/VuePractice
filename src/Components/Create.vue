<template>
    <div id='createBox'>
        <div id='inputBoxes'>
            <input type="text" placeholder="Bot Name" required v-model="botName" >
            <input type="number" placeholder="Attack Value" required v-model="attack">
            <input type="number" placeholder="Health Value" required v-model="health">
            <input type="text" placeholder= "Image URL" required v-model="img">
        </div>
        <div id='buttons' >
            <button @click="addBot">Submit</button>
            <button>Clear</button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['bots', 'showCollection'],
    data:{
        id: 0,
        botName: '',
        attack: null,
        health: null,
        img: ''
    },
    methods:{
        addBot(id){
            id++
            let newBot={
                botName:this.botName,
                attack: this.attack,
                health: this.health,
                img: this.img
            }
            this.bots.push(newBot)
            this.showCollection()
        }
    }
};
</script>

 <style scoped>
 #createBox{
     background: whitesmoke;
     width: 500px;
     height: 350px;
     margin: auto;
     margin-top: 10vh;
     border-radius: 5px;
     display: flex;
     flex-direction: column;
 }
#inputBoxes{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    margin-left: 20%;
    margin-right: 20%;
    height: 80%;
}
#buttons{
   width: 40%;
   display: flex;
   justify-content: space-between;
   margin: auto;
}
input{
    padding: 10px;
    border-radius: 3px;
    border: none;
    border-bottom: thick #4dd9e5 solid;
    background: whitesmoke;
    text-align: center;
    font-size: 1em;
    outline: none;
}
</style>