<template>
<!-- 컴포넌트로 만들 수 있는 최소단위로 컴포넌트를 만들어보자 -->
<!-- 버튼 태그를 쓰지 않고 커스텀해서 사용하는 방법: 버튼 모양만 만들어 놓고 이름은 메인페이지에서 직접 사용가능 -->
    <div class="btn">
        <slot >일반버튼</slot>
        <!-- slot은 부모 컴포넌트가 자식 컴포넌트의 특정 위치에 내용을 삽입할 수 있게 해주는 태그 -->
        <slot name="text">일반버튼</slot>
        <slot name="icon">일반버튼</slot>
    </div>

    <!-- <div></div> -->
    <!-- 컴포넌트안에서는 태그가 하나만 있어야함, 그렇지 않으면 메인페이지에서 커스텀 할때 어디에 적용해야할지몰라서
    의도한 결과가 나오지 않을수 있다.-->

    <!-- <h1 :class="$attrs.class" :style="$attrs.style">Test</h1> -->
</template>

<script>
export default {
    //inheritAttrs : false,
    //inheritAttrs 옵션을 false로 설정하면, 부모 컴포넌트에서 전달된 속성이 자식 컴포넌트의 루트 요소에 자동으로 적용되지 않습니다.
    //created(){
    //    console.log(this.$attrs)
    //}
    //Vue 컴포넌트는 기본적으로 부모로부터 전달받은 모든 속성을 루트 요소에 적용합니다.
    //$attrs는 자식 컴포넌트로 전달된 속성들을 객체 형태로 보유합니다.
}
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