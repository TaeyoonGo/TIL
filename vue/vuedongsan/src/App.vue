<template>
    <div>
        
            <div class="menu">
                <a v-for="(작명,i) in 메뉴들" :key="i">{{작명}}</a>
            </div>

            <div class="black-bg" v-if="모달창열렸니 == true">
              <div class="white-bg">
                  <h4 @click="모달창열렸니 = false">상세페이지임</h4>
                  <p>상세페이지 내용임</p>ss
              </div>
            </div>

            <div>
                <p :style="스타일">{{logo}}</p>
                <h4 @click="모달창열렸니 = true">{{products[0]}}</h4>
                <p>{{price1}}
                    만원</p>
            </div>
              <button @click="increase">허위매물신고</button><span>신고수 : {{신고수}}</span>
            <div>
                <h4>{{products[1]}}</h4>
                <p>{{price2}}
                    만원</p>
            </div>
            <div>
                <h4>{{products[2]}}</h4>
                <p>{{price2}}
                    만원</p>
            </div>
        </div>
    </template>

    <script>

        export default {
            name: 'App',
            data() {
                return {
                    모달창열렸니 : false,
                    신고수 : 0,
                    메뉴들: [
                        'Home', 'Shop', 'About'
                    ],
                    price1: 80,
                    price2: 70,
                    logo: '원룸샵',
                    스타일: 'color : blue',
                    products: ['역삼동원룸', '천호동원룸', '마포구원룸']
                }
            },

            methods: {
              increase(){
                this.신고수 += 1;
              }
            },
            components: {}
        }
    </script>

    <style>
        #app {
            font-family: Avenir, Helvetica, Arial, sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            text-align: center;
            color: #2c3e50;
            margin-top: 60px;
        }
        .menu {
            background: darkslateblue;
            padding: 15px;
            border-radius: 5px;
        }
        .menu a {
            color: #fff;
            padding: 10px;
        }
        .black-bg{
          width: 100%;
          height: 100%;
          background: rgba(0, 0, 0, 0.5);
          position: fixed; padding: 20px;
        }
        .white-bg{
          width: 100%;
          background: #fff;
          border-radius: 8px;
          padding: 20px;;
        }
    </style>