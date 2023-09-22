<template>
    <h1>Hello, {{title}}!</h1>
    <div>{{htmlString}}</div>
    <div v-html="htmlString"></div>
    <input type="text" v-model="valueModel" />
    <input type="number" v-model.number="numberModel" />
    <div>
        <textarea v-model="message"></textarea>
    </div>
    <div>
        <select v-model="city">
            <option value="02">서울</option>
            <option value="21">부산</option>
            <option value="064">제주</option>
        </select>
    </div>
    <div>
        <!--<label><input type="checkbox" v-model="checked"> {{ checked }}</label>-->
        <label><input type="checkbox" v-model="checked" true-value="yes" false-value="no"> {{ checked }}</label>
    </div>
    <div>
        <label><input type="checkbox" value="서울" v-model="checked2">서울</label>
        <label><input type="checkbox" value="부산" v-model="checked2">부산</label>
        <label><input type="checkbox" value="제주" v-model="checked2">제주</label>
        <br>
        <span>체크 지역 : {{ checked2 }}</span>
    </div>
     <div>
        <label><input type="radio" v-bind:value="radioValue1" v-model="picked">서울</label>
        <label><input type="radio" v-bind:value="radioValue2" v-model="picked">부산</label>
        <label><input type="radio" v-bind:value="radioValue3" v-model="picked">제주</label>
        <br>
        <span>체크 지역 : {{ picked }}</span>
    </div>
    <div>
        <img v-bind:src="imgSrc" />
    </div>
    <div>
        <input type="text" v-model="textValue" />
        <button type="button" v-bind:disabled="textValue==''">Click</button>
    </div>
</template>
<script>

export default{ 
    data(){ // 데이터 변수 
        return{
            title: 'World',
            htmlString: '<p style="color:red;">This is a red string.</p>',
            valueModel: 'South Korea',
            numberModel: 3,
            message: "여러 줄을 입력할 수 있는 textarea",
            city: "064",
            checked: true,
            checked2: [],
            picked: '',
            radioValue1: '서울',
            radioValue2: '부산',
            radioValue3: '제주',
            imgSrc: require('@/assets/images/penguin.jpg'), // require : 해당 경로를 import 한다
            textValue: ""
        };
    },
    setup(){}, // 컴포넌트 API 
    created(){}, // 컴포넌트 생성 
    mounted(){}, // html 랜더링 후 
    unmounted(){}, // unmount 완료 후 
    methods:{} // 컴포넌트 내 메소드 
}
</script>