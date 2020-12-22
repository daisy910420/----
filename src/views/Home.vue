<template>
    <div class="Week10">
        <h1>{{ title }}</h1>
        <h1>{{ title }}</h1>
        <div id="form">
            <div class="name-card-area" v-for="(item, index) in nameCards" :key="index">
                <div class="block firstname">{{ firstNameTitle }}:
                    <input type="text" name="firstname" v-model="item.name" />
                </div>
                <div class="block"></div>
                <div class="block sex">{{ sexTitle }}:
                    <input type="radio" name="sex" />
                    {{ item.sex }}
                </div>
                <div class="block location">{{ bornTitle }}:
                    <select name="location" v-model="item.born">
                        <option :value="option" v-for="(option, index) in location" :key="index">{{ option }}</option>
                    </select>
                </div>
            </div>
            <div class="name-card-area">
                <div class="block firstname">{{ firstNameTitle }}: {{addCard.name}}
                    <input type="text" name="firstname" v-model="addCard.name" />
                </div>
                <div class="block"></div>
                <div class="block sex">{{ sexTitle }}:
                    <input type="radio" name="sex" />
                </div>
                <div class="block location">{{ bornTitle }}: {{addCard.born}}
                    <select name="location" v-model="addCard.born"> 
                        <option :value="option" v-for="(option, index) in location" :key="index">{{ option }}</option>
                    </select>
                </div>
            </div>
            <div class="btn">
                <button v-on:click="addNameCard()">增加</button>
            </div>
            <div class="div">{{ btnText }}</div>
        </div>
    </div>
</template>

<script>
export default {
    name:'Week10',
    data() {
        return {
            btnText: '',
            check: 12,
            show: false,
            hightline: true,
            title: '表單超級練習~~~',
            firstNameTitle: '姓名',
            lastNameTitle: '姓氏',
            sexTitle: '性別',
            bornTitle: '出生地',
            addCard : {
            name: '',
            sex: '',
            born: '',
            }, 
        
            nameCards: [
            {
                name: 'Warrick Tsai',
                sex: '中性',
                born: '台北市',
            },
            {
                name: 'Frank Ho',
                sex: '女',
                born: '新竹市',
            },
            {
                name: 'May Li',
                sex: '男',
                born: '台中市',
            },
            {
                name: 'May Lu',
                sex: '男',
                born: '新竹市',
            },
            {
                name: 'May Tsai',
                sex: '男',
                born: '苗栗縣',
            }
            ],
            
                location: [
                '新竹市',
                '台北市',
                '台中市',
                '苗栗縣',
            ],
        }
    },
    methods:{
        addNameCard() {
            var tmp =Object.assign({},this.addCard)
            this.nameCards.push(tmp);
            this.addCard.name='';
            this.addCard.born='';
        }
    },
}
</script>

<style>
.form {
    border: solid 1px black;
    padding: 10px;
    }

.top-border {
    border-top: solid 1px grey;
    }

.name-card-area {
    padding: 10px;
    }

.padding-left-20 {
    padding-left: 20px;
    }

</style>