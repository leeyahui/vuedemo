<template>
    <div>
        <h1>to do list</h1>
        <input type="text" v-model="inputvalue" />
        <button @click="handlerAdd">提交</button>
        <ul>
            <li v-for="(item,index) in list" :key="index" @click="handlerDelete">
                {{item}}
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                inputvalue: '',
                list: []
            }
        },
        methods: {
            handlerAdd: function () {
                this.list.push(this.inputvalue)
                this.inputvalue = ''
            },
            handlerDelete: function (index) {
                this.list.splice(index, 1)
            }
        }
    }
</script>