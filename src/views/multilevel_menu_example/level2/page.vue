<template>
    <div>
        <page-main v-for="item in data" :key="item.id">
            <h1>{{ item.text }}</h1>
            <h6>创建时间{{ item.createTime }}</h6>
            <h5>总结：{{item.summary}}</h5>
            <h5>内容:{{item.content}}</h5>
            <el-button type="primary">查看网页代码</el-button>
        </page-main>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            count: 0,
            data: [],
            value: ''
        }
    },
    created() {
        axios.get('http://127.0.0.1:4523/mock/383869/sso/getAuthCode').then(response => {
            // this.data = JSON.stringify(response.data.data)
            this.data = response.data.data
            console.log(this.data)

        })
    },
    methods: {
        stringToHtml(e, str) {
            console.log(e, str)
            // var result = []
            // var list = str.split('-')
            // for (var i = 0; i < list.length; i++) {
            //     var item = list[i]
            //     if (item.length < 8) {
            //         result.push(item)
            //         continue
            //     }
            //     var asciiCode = parseInt(item, 2)
            //     var charValue = String.fromCharCode(asciiCode)
            //     result.push(charValue)
            // }
            // return result.join('')
        }
    }
}
</script>
<!--<script>-->
<!--function syntaxHighlight(json){-->

<!--    if(typeofjson!='string'){-->

<!--        json=JSON.stringify(json,undefined,2);-->

<!--    }-->

<!--    json=json.replace(/&/g,'&').replace(/</g,'<').replace(/>/g,'>');-->

<!--    returnjson.replace(/("(\\u[a-zA-Z0-9]{4}|\\[^u]|[^\\"])*"(\s*:)?|\b(true|false|null)\b|-?\d+(?:\.\d*)?(?:[eE][+\-]?\d+)?)/g,function(match){-->

<!--        varcls='number';-->

<!--        if(/^"/.test(match)){-->

<!--            if(/:$/.test(match)){-->

<!--                cls='key';-->

<!--            }else{-->

<!--                cls='string';-->

<!--            }-->

<!--        }elseif(/true|false/.test(match)){-->

<!--            cls='boolean';-->

<!--        }elseif(/null/.test(match)){-->

<!--            cls='null';-->

<!--        }-->

<!--        return'<spanclass="'+cls+'">'+match+'</span>';-->

<!--    });-->

<!--}-->
<!--</script>-->
