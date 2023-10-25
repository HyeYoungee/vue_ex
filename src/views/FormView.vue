<script>
export default{
  data() {
    return{
      message: '',
      multiple: '',
      checked: true,
      checkedNames: [],
      picked: '하나',
      selected: '',
      options: [
        { text: '하나', value: '1' },
        { text: '둘', value: '2' },
        { text: '셋', value: '3' }
      ],
      dynamicTrueValue: '네',
      dynamicFalseValue: '아니오',
      pick: '',
      first: '네',
      second: '아니오',
      msg: ''
    }
  }
}
</script>

<template>
  <div class="layout">
    <h1>This is an Form Input Bindings page</h1>

    <h2>텍스트</h2>
    <input type="text" :value="message" @input="event => message = event.target.value">
    <!-- <input v-model="message"> -->
    <!-- 한글은 v-model 사용XX -->
    <p>메시지: {{ message }}</p>

    <hr>
    <h2>여러 줄 텍스트</h2>
    <span>여러 줄 메세지:</span>
    <p style="white-space: pre-line;">{{ multiple }}</p>
    <textarea v-model="multiple" placeholder="여러 줄을 추가해보세요"></textarea>

    <hr>
    <h2>체크박스</h2>
    <input type="checkbox" id="checkbox" v-model="checked" />
    <label for="checkbox">&nbsp;{{ checked }}</label>

    <div>체크된 이름: {{ checkedNames }}</div>
    <input type="checkbox" id="jack" value="젝" v-model="checkedNames">
    <label for="jack">젝&nbsp;&nbsp;</label>

    <input type="checkbox" id="john" value="존" v-model="checkedNames">
    <label for="john">존&nbsp;&nbsp;</label>

    <input type="checkbox" id="mike" value="마이크" v-model="checkedNames">
    <label for="mike">마이크</label>

    <hr>
    <h2>라디오</h2>
    <div>선택한 것: {{ picked }}</div>

    <input type="radio" id="one" value="하나" v-model="picked" />
    <label for="one">하나</label>

    <input type="radio" id="two" value="둘" v-model="picked" />
    <label for="two">둘</label>

    <hr>
    <h2>셀렉트</h2>
    <div>선택됨: {{ selected }}</div>
    
    <select v-model="selected">
      <option disabled value="">다음 중 하나를 선택하세요</option>
      <option value="a">가</option>
      <option value="b">나</option>
      <option value="c">다</option>
    </select>

    <h2>셀렉트 v-for 동적 렌더링</h2>
    <select v-model="selected">
      <option v-for="option in options" :value="option.value" :key="option">
        {{ option.text }}
      </option>
    </select>

    <div>선택됨: {{ selected }}</div>

    <hr>
    <h2>값 바인딩 하기</h2>
    <!-- `picked`는 선택 시 문자열 "가"입니다. -->
    <input type="radio" v-model="picked" value="가" />

    <!-- `toggle`은 true 또는 false입니다. -->
    <input type="checkbox" v-model="toggle" />

    <!-- `selected`는 첫 번째 옵션이 선택될 때 문자열 "한글"입니다. -->
    <select v-model="selected">
      <option value="한글">한글</option>
    </select>

    <hr>
    <h2>Checkbox</h2>
    <input
      type="checkbox"
      v-model="toggle"
      :true-value="dynamicTrueValue"
      :false-value="dynamicFalseValue" />
    <!-- {{ toggle }} -->
    
    <h2>radio</h2>
    <input type="radio" v-model="pick" :value="'first'" />
    <input type="radio" v-model="pick" :value="'second'" />
    {{ pick }}

    <hr>
    <h2>수식어 - lazy</h2>
    <!-- "input" 대신 "change" 이벤트 후에 동기화됨 -->
    <input v-model="msg" /> <!--  input이벤트 발생 -->
    <input v-model.lazy="msg" /> <!--  change이벤트 발생 -->
    {{ msg }}


  </div>
</template>

<style>

</style>