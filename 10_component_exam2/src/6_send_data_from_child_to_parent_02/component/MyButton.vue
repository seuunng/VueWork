<template>
    <div class="btn">
        <slot></slot>
    </div>
    <h1 @click="onclick">Test</h1> <!--클릭할때마다 이벤트 발생-->
    <input type="text" v-model="text"/> <!--텍스트영역에 사용자 입력값 사용하기-->
</template>

<script>
export default {
    emits : ["logChild"],
    // changeMessage도 emits로 전달하지만 정의하지 않음 근데도 실행은 잘됨
    // 지피티에 답변: changeMessage 이벤트는 emits 옵션에서 정의되지 않았지만, 
    // 여전히 이벤트는 정상적으로 발생합니다. 이는 Vue의 유연성 덕분입니다. 
    // 하지만, emits 옵션을 사용하여 발생 가능한 모든 이벤트를 정의하는 것이 좋습니다. 
    // 이는 코드의 명확성과 유지보수성을 높이고, 
    // 팀원들이나 사용하는 사람들에게 컴포넌트의 인터페이스를 명확히 전달할 수 있습니다.
    data(){
        return {
            text: "" //v-model로 넘기는 값 사용
        }
    },
    methods:{
      onclick(){ //emits 옵션은 어떤 이벤트를 발생시킬 수 있는지 명시적으로 정의
        this.$emit('logChild',this.text);
      },
    },
    watch:{ //watch 옵션: 특정 데이터 속성이나 계산된 속성이 변경될 때 실행할 로직을 정의
        text(){
        this.$emit('changeMessage',this.text);
        }
    }
}
/*
computed를 사용할 때:
다른 데이터 속성에 의존하여 계산된 값을 사용할 때.
값이 캐싱되어 성능 최적화가 필요할 때.
단순히 값을 반환하는 경우.
watch를 사용할 때:
데이터 변화에 따른 비동기 작업이나 부수 효과가 필요할 때.
데이터 변경에 따른 복잡한 로직을 수행해야 할 때.
의존하는 데이터가 변경될 때마다 특정 함수를 실행해야 할 때.
*/
</script>

<style>
    .btn {
        display: inline-block;
        padding: 6px;
        margin: 4px;
        border-radius: 4px;
        background-color: gray;
        color: white;
        cursor:pointer;
    }
</style>