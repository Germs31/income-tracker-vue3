<template>
  <form @submit.prevent="FormHandler">
      <input type="text" placeholder="...description" v-model="FormData.desc"/>
      <input type="number" placeholder="...value" v-model="FormData.value"/>
      <input type="date" placeholder="...date" v-model="FormData.date"/>
      <input type="submit" value="submit">
  </form>
</template>

<script>
import { reactive } from 'vue'
export default {
    props: {
        state: Object
    },
    setup(props, {emit}){
        const FormData = reactive({
            desc: null,
            value: null,
            date: null
        })

        function FormHandler () {
            emit("add-income", {
                desc: FormData.desc,
                value: FormData.value,
                date: FormData.date
            })

            FormData.desc = null;
            FormData.value = null;
            FormData.date = null;
        }

        return {
            FormHandler,
            FormData
        }
    }
}
</script>

<style  scoped>
    form {
        display: flex;
        justify-content: center;
        margin-top: 30px;
    }

    form input {
        color: #888;
        border: none;
        outline: none;
        font-size: 20px;
    }

    form input::placeholder {
        color:#aaa;
    }

    form input:not([type="submit"]){
        display: block;
        background: #fff;
        border: none;
        outline: none;
        padding: 5px 15px;
    }

    form input[type="submit"]{
        display: block;
        background: none;
        border: none;
        outline: none;
        padding: 5px 15px;
        color: #fff;
        font-weight: 500;
        text-shadow: 0 1px 3px rgba(0,0,0,0.2);
        padding: 5px 15px;
        background-color: #ffce00;
        cursor: pointer;
    }

    form input:first-of-type{
        border-radius: 8px 0 0 8px;
    }

    form input:last-of-type{
        border-radius: 0 8px 8px 0;
    }
</style>