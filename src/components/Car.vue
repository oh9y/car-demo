<template>
    <div>
        <table>
            <thead>
                <tr>
                    <th>名称</th>
                    <th>数量</th>
                    <th>价格</th>
                    <th>操作</th>
                </tr>
            </thead>
            <tbody>
                <tr :key="index" v-for="(item, index) in data">
                    <td>{{ item.name }}</td>
                    <td><button @click="addAndSub(item,false)">-</button>{{ item.num }}<button @click="addAndSub(item,true)">+</button></td>
                    <td>{{ item.price*item.num }}</td>
                    <td><button>删除</button></td>
                </tr>
            </tbody>
            <tfoot>
                <td>总价{{ $total  }}</td>
            </tfoot>
        </table>
    </div>
</template>

<script setup lang='ts'>
import { reactive, toRefs,ref,computed } from 'vue'
interface Shop {
    name: string,
    num: number,
    price: number
}


let $total = ref<number>(0)
$total = computed(()=>{
    return data.reduce((prev,next)=>{
        return prev + next.num*next.price
    },0)
})

const data = reactive<Shop[]>([
    {
        name: '衣服',
        num: 1,
        price: 100
    },
    {
        name: '裤子',
        num: 1,
        price: 200
    },
    {
        name: '鞋子',
        num: 1,
        price: 300
    },])

const addAndSub = (item:Shop,type:boolean):void=>{
    if(item.num>0 &&!type){
        item.num--
         
    }
    if(item.num<9 &&type){
        item.num++
        
    }
}


</script>
<style scoped lang='less'>
th {
    text-align: center;
}

td {
    text-align: center;
}</style>