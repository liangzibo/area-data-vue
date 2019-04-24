# area-data-vue
省市区街道数据

## 安装 vue-area-linkage

使用npm安装:

```
    npm i --save vue-area-linkage
```
## 安装 area-data-vue

```
    npm i --save area-data-vue
```

## 使用
```
    import Vue from 'vue';
    import VueAreaLinkage from 'vue-area-linkage';
    Vue.use(VueAreaLinkage)
```

```
    <template>
        <div>
            <area-select v-model="selected" :data="pcaa"></area-select>         // 省市区
            <area-cascader v-model="selected2" :data="pcaa"></area-cascader>    // 省市区
        </div>
    </template>
    <script>
        import { pcaa } from "area-data-vue"; // 城市数据
        import "vue-area-linkage/dist/index.css"; // 样式
        export default {
          name: "Test",
          data() {
            return {
              pcaa: pcaa,
              selected: [],
              selected2: []
            }
          }
        }
    </script>
```


## 属性

### area-select 组件

|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholders | Array | - | [] | 设置 placeholder text |
| level | Number | 0/1/2 | 1 | 设置联动层级(0-只选省份/1-省市联动/2-省市区联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据(v5需要传入) |
| icon | String | - | area-select-icon | 自定义下拉小图标 |
| disableLinkage | Boolean | - | true | 地区选择是否进行联动 |

>v4 仅支持省市区联动，即 v4 不再支持 level 的值为 3(省市区街联动)

### area-cascader 组件
|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholder | String | - | '' | 设置 placeholder text |
| level | Number | 0/1 | 0 | 设置联动层级(0-省市联动/1-省市区联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| separator | String | - | '-' | 显示选中文本的分隔符 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据(v5需要传入) |

## 事件

|  事件名  |  说明  |  参数 |
|  :--:  |  :--:  |  :--: |
| change | 选中值发生变化时触发 | 目前选择的值 |
