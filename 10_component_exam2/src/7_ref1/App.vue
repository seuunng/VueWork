<template>
  <div id="app">
    <H1 id="h1">Hello World!!!</H1>
    <H1 ref="h1_2">Hello World!!!22</H1>
    <hello ref="good2"></hello><!--컴포넌트 불러오기-->
  </div>
</template>
<script>
import Hello from './component/Hello.vue'

export default{
  name : 'App',
  components:{
    Hello
  },
  methods:{

  },
  mounted(){
    //자바스크립트시절 돔방식으로 접근
    let h1 = document.querySelector('h1');
    console.log(h1);
    //자바스크립트시절 해당태그의 내용 꺼내오기
    let text = h1.textContent;
    console.log(text);
    //뷰스타일로 접근, ref이용
    console.log(this.$refs.h1_2.textContent);
    //컴포넌트에 있는 태그에 접근할때
    console.log(this.$refs.good2.$refs.good.textContent);
    console.log(this.$refs.good2.$el);
    //$el: 태그정보 가져오기(태그에 어떤 속성으로 접근할 수 있는지 확인할 수 있음)
  },

}
</script>

  
