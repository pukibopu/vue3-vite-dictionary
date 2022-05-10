<template>
    <header>
        <h2 class="title">{{wordValue? wordValue:'World Hunt'}}</h2>
        <div class="input-wrap">
            <input type="text" placeholder="Search a Word" v-model="wordValue"
            @input="$emit('update:modelValue',$event.target.value)"
            >

        </div>
    </header>
</template>
<script setup lang="ts">
import { ref } from 'vue'
interface emitType{
    (e: 'update:modelValue', value:any): void
}
const wordValue = ref<string>()
defineEmits<emitType>()
</script>
<style lang="scss" scoped>
header{
    height: 30vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    h2 {
        font-size: 7vw;
        font-weight: 100;
        @media (max-width:1000px) {
            font-size: 11vw;
        }
    }
    .input-wrap {
        input {
             width: 50vw;
             border: none;
             background-color: #282c34;
             border-bottom: 1px solid rgba(197,188,188);
             padding: 5px;
             color: #fff;
             font-size: 18px;
             &:focus {
                 outline: none;
                 border-bottom: 1px solid #fff;
             }
             &::placeholder {
                 color: rgba($color: #fff,$alpha: 0.6);
             }
        }
    }
}
</style>
