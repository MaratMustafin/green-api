<script setup>
  import { ref } from "vue";
  import Input from './components/Input.vue';
  import Button from './components/Button.vue';
  import Textarea from "./components/Textarea.vue";
  import Output from "./components/Output.vue";


  const instanceId = ref("");
  const apiToken = ref("");
  const output = ref("");
  const phoneNumber = ref("");
  const message = ref("");
  const fileUrl = ref("");


  async function get(type) {
    const url = new URL(`https://api.green-api.com/waInstance${instanceId.value}/${type}/${apiToken.value}`);
    const response = await fetch(url.href, {
      method: "GET",
      mode: "cors",
    })
    output.value = JSON.stringify(await response.json(),undefined, 4);
  }



  function changeBody(type) {
    const types = {
    "sendMessage": {
        "chatId": phoneNumber.value + '@c.us',
        "message": message.value
      },
    "sendFileByUrl": {
        "chatId": phoneNumber.value + '@c.us',
        "urlFile": fileUrl.value,
        "fileName": "cat.png",
        "caption": "cat",
      }
    }
    return types[type];
  }


  async function post(type) {
    const body = changeBody(type);
    const url = new URL(`https://api.green-api.com/waInstance${instanceId.value}/${type}/${apiToken.value}`);
    const response = await fetch(url.href, {
      method: "POST",
      mode: "cors",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(body)
    })
    output.value = JSON.stringify(await response.json(),undefined, 4);
  }
  
</script>

<template>
  <main>
    <div class="functions-api">
      <div class="form-group">
        <Input type="text"  placeholder="Type instanceId" v-model="instanceId" />
        <Input type="text"  placeholder="Type apiToken" v-model="apiToken"/>
        <Button text="getSettings" @click="get('getSettings')" />
        <Button text="getStateInstance" @click="get('getStateInstance')" />
      </div>
      <div class="form-group">
        <Input type="text" placeholder="Type phone number" v-model="phoneNumber"  />
        <Textarea placeholder="Type message" v-model="message" />
        <Button text="sendMessage" @click="post('sendMessage')"/>
      </div>
      <div class="form-group">
        <Input type="text" placeholder="Type phone number" v-model="phoneNumber"  />
        <Input type="text" placeholder="Type file url" v-model="fileUrl" />
        <Button text="sendFileByUrl" @click="post('sendFileByUrl')" />
      </div>
    </div>
    <div class="answer-output">
        <Output label="Output:" :output="output" />
    </div>
  </main>
</template>

<style scoped>
main {
     display: grid;
     grid-template-columns: minmax(auto, 400px) auto;
     width: 100%;
     height: 100vh;
     background-color: #fff;
     color: #222222;
     box-sizing: border-box; 
}

main .functions-api {
    height: 100%;
    overflow-y: auto;
    border-right: 2px dotted #4cae4f;
      
}
main .functions-api .form-group {
    display: flex;
    flex-direction: column;
    padding-top: 2em;
    padding-bottom: 2em;
    border-bottom: 2px dotted #4cae4f;
}
</style>