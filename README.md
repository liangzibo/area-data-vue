![npm-version](https://img.shields.io/npm/v/vue-area-linkage.svg) ![license](https://img.shields.io/npm/l/vue-area-linkage.svg)
# area-data-vue
省市区街道数据

## Installation
Install the pkg with npm:
```
npm i --save area-linkage-vue area-data-vue
```

## Usage
```
import Vue from 'vue';
import { pcaa } from 'area-data-vue';
import 'area-linkage-vue/dist/index.css';
import AreaLinkageVue from 'area-linkage-vue';
Vue.prototype.$pcaa = pcaa;

Vue.use(AreaLinkageVue)
```

```
<area-select v-model="selected" :data="$pcaa" :level="0"></area-select>  // 省
<area-select v-model="selected" :data="$pcaa" :level="1"></area-select>  // 省市
<area-select v-model="selected" :data="$pcaa" :level="2"></area-select>  // 省市区：
<area-select v-model="selected" :data="$pcaa" :level="3"></area-select>  // 省市区街道：

<area-cascader v-model="selected2" :data="$pcaa" :level="0"></area-cascader>  // 省市
<area-cascader v-model="selected2" :data="$pcaa" :level="1"></area-cascader> // 省市区：
<area-cascader v-model="selected2" :data="$pcaa" :level="2"></area-cascader> // 省市区街道：

```



## 属性
### area-select 组件
|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholders | Array | - | [] | 设置 placeholder text |
| level | Number | 0/1/2/3 | 1 | 设置联动层级(0-只选省份/1-省市联动/2-省市区联动/3-省市区街道联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据 |
| icon | String | - | area-select-icon | 自定义下拉小图标 |
| disableLinkage | Boolean | - | true | 地区选择是否进行联动 |


### area-cascader 组件
|  参数  |  类型  |  可选值  |  默认值  |  说明  |
|  :--:  |  :--:  |  :--:  |  :--:  |  :--:  |
| type | String |  all/code/text | code | 设置返回的数据格式 |
| placeholder | String | - | '' | 设置 placeholder text |
| level | Number | 0/1/2 | 0 | 设置联动层级(0-省市联动/1-省市区联动/2-省市区街道联动) |
| size | String | small/medium/large | medium | 设置输入框的大小 |
| separator | String | - | '-' | 显示选中文本的分隔符 |
| disabled | Boolean | - | false | 是否禁用 |
| data | Object | - | - | 地区数据 |

## 事件

|  事件名  |  说明  |  参数 |
|  :--:  |  :--:  |  :--: |
| change | 选中值发生变化时触发 | 目前选择的值 |


## License
MIT.

