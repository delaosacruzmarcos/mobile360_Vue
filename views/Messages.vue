<template>
    <div class="container-fluid">
        <div class="row text-left">
        
            <!-- Message list div start -->
            <div class="col-3 col-lg-3 col-md-3 col-sm-3">
                <div class="card">

                    <div class="card-header">
                        Messaging
                    </div>

                    <ul class="list-group">
                        <li :key="index" v-for="(message,index) in messages" @click="uSelectedConvo(message)" class="text-left list-group-item">
                            <p>{{message.name}}</p>
                            <p>{{lastMessage(message)}}</p>
                        </li>
                        <hr>
                    </ul>

                    <div class="card-footer text-muted"></div>
                </div>
            </div>
            <!-- Message list div end -->

            <!-- Conversations div start -->
            <div class="col-6 col-lg-6 col-md-6 col-sm-6">
                <div class="card text-left">

                    <div class="card-header">
                        <strong>{{selectedPerson}}</strong>
                    </div>

                    <ul v-if="chatSelected == true" class="list-group">
                        <li :key="index" v-for="(msg,index) in selectedConvos" class="text-left list-group-item">
                            <p>{{msg}}</p>
                        </li>
                    </ul>

                    <ul v-else class="list-group">
                        <p>{{uSelectedConvo(messages[0])}}</p>
                        <li :key="index" v-for="(msg,index) in selectedConvos" class="text-left list-group-item">
                            <p>{{msg}}</p>
                        </li>
                    </ul>
                    
                    <div v-if="chatSelected == true" class="row card-footer text-muted">
                        <div class="col-6"><input v-model="currentMsg" placeholder="Type here" id="inputText"></div>
                        <div class="col-2"><button class="col btn btn-sm btn-outline-success" @click="send()">Send</button></div>
                        
                    </div>
                    
                </div>
            </div>
            <!-- Conversations div end -->

            <!-- Promotions div start -->
            <div class="col-3 col-lg-3 col-md-3 col-sm-3">
                <div class="card text-left">
                    <div class="card-body">
                        <h5 class="card-title">Your ad goes here</h5>
                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                        <a href="#" class="card-link">Ad link</a>
                    </div>
                    <hr>
                    <div class="card-body">
                        <h5 class="card-title">Your ad goes here</h5>
                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                        <a href="#" class="card-link">Ad link</a>
                    </div>
                </div>
            </div>
            <!-- Promotions div end -->

        </div>
    </div>
</template>

<script>
export default {
    name:'Messages',
    data(){
        return{
            messages:[{
                name:'Shivaleela Hubli',
                displayName: 'Shivaleela',
                conversations: [
                    [{'msg': 'Hello!'}, 0], 
                    [{'msg': 'Hi'}, 1],
                    [{'msg': 'Is the connection page completed?'}, 0], 
                    [{'msg': 'Almost'}, 1], 
                    [{'msg': 'How about the message page?'}, 1], 
                    [{'msg': 'Yeah almost'}, 0],
                    [{'msg': 'Okay'}, 1]]
            },
            {
                name:'Chin Ya Russell',
                displayName: 'Chin',
                conversations: [
                    [{'msg': 'Hello!'}, 0], 
                    [{'msg': 'Hi'}, 1],
                    [{'msg': 'How are you?'}, 0], 
                    [{'msg': 'How is the work going on?'}, 0], 
                    [{'msg': 'It is great!'}, 1], 
                    [{'msg': 'Thank you for the demo!'}, 0],
                    [{'msg': 'You are welcome!'}, 1]]
            },
            {
                name:'Sejal Agarwal',
                displayName: 'Sejal',
                conversations: [
                    [{'msg': 'Hello!'}, 0], 
                    [{'msg': 'Hi'}, 1],
                    [{'msg': 'How are you?'}, 0], 
                    [{'msg': 'I am fine. How are you doing?'}, 1], 
                    [{'msg': 'It am great! Thank you'}, 1],
                    [{'msg': 'Have a happy weekend!'}, 0],
                    [{'msg': 'Thank you!'}, 1]]
            }],
            selectedPerson: 'Shivaleela Hubli',
            chatSelected: false,
            currentMsg: ''
        }
    },
    methods:{

        uSelectedConvo(selectedItem){
            this.chatSelected = true;
            this.selectedPerson = selectedItem.name;
            var formatted = [];

            for (var i = 0; i < selectedItem.conversations.length; i++) {
                if(selectedItem.conversations[i][1] == 0){
                    formatted[i] = selectedItem.displayName + " : " + selectedItem.conversations[i][0].msg;
                }
                else{
                    formatted[i] = "Me : " + selectedItem.conversations[i][0].msg;
                }
            }
            
            this.selectedConvos = formatted;
        },

        lastMessage(selectedItem){
            var index = selectedItem.conversations.length - 1;
            return(selectedItem.conversations[index][0].msg);
        },

        send(){
            this.messages.forEach(element => {
                if(element.name==this.selectedPerson){
                    element.conversations.push(
                        [{'msg': this.currentMsg}, 1]
                    )
                    this.uSelectedConvo(element);
                }
            })
            this.currentMsg='';
            console.log(this.currentMsg);
        }
    }
}
</script>

<style scoped>
li{
    cursor: pointer;
}

p{
 margin:0;
}

#inputText {
    width: auto;
}

input {
    width: 100%;
}

</style>