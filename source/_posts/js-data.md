---
title: js里的数据。
---

### 数据类型

七种数据类型（请背诵）：number string boolean symbol undefined null object 注意没有 array 类型也没有 function 类型。
#### number
	•	整数和小数：1 1.1 .1
	•	科学记数法：1.23e2
	•	二进制：0b11
	•	八进制：011（后来 ES5 添加了 0o11 语法）
	•	十六进制：0x11
#### string
	•	空字符串：''
	•	多行字符串：
	•	  var s = '12345' +
	•	              '67890' // 无回车符号
	•	  或
	•	  var s = `12345
	•	  67890` // 含回车符号
#### boolean
	•	乔治·布尔 乔治·布尔是英格兰数学家和哲学家、数理逻辑学先驱。 由于其在符号逻辑运算中的特殊贡献，很多计算机语言中将逻辑运算称为布尔运算，将其结果称为布尔值。 1864年，布尔冒着大雨步行两英里走到讲台，身着打湿的衣服为学生们授课。不久后，他就病倒了，得了重度感冒还发高烧。其妻错误地相信疾病需要用致病因子施救，因为布尔是淋雨水而感冒的，妻子于是用桶子装水淋到他身上。结果湿气进一步加剧了他的病情。1864年，12月8日，布尔死于肺部积水。 上面资料的来源是维基百科，请自行选择是否相信。
	•	boolean 的取值 只有两个值：true 和 false a && b 在 a 和 b 都为 true 时，取值为 true；否则为 false a || b 在 a 和 b 都为 false 时，取值为 false；否则为 true
#### symbol JS 中的 Symbol 是什么？
ES 6 引入了一个新的数据类型 Symbol，它是用来做什么的呢？

为了说明 Symbol 的作用，我们先来描述一个使用场景。

我们在做一个游戏程序，用户需要选择角色的种族。

var race = {
  protoss: 'protoss', // 神族
  terran: 'terran', // 人族
  zerg: 'zerg' // 虫族
}

function createRole(type){
  if(type === race.protoss){创建神族角色}
  else if(type === race.terran){创建人族角色}
  else if(type === race.zerg){创建虫族角色}
}
那么用户选择种族后，就需要调用 createRole 来创建角色：

// 传入字符串
createRole('zerg') 
// 或者传入变量
createRole(race.zerg)
一般传入字符串被认为是不好的做法，所以使用 createRole(race.zerg) 的更多。

如果使用 createRole(race.zerg)，那么聪明的读者会发现一个问题：race.protoss、race.terran、race.zerg 的值为多少并不重要。



改为如下写法，对 createRole(race.zerg) 毫无影响：

var race = {
  protoss: 'askdjaslkfjas;lfkjas;flkj', // 神族
  terran: ';lkfalksjfl;askjfsfal;skfj', // 人族
  zerg: 'qwieqwoirqwoiruoiwqoisrqwroiu' // 虫族
}
也就是说：

race.zerg 的值是多少无所谓，只要它的值跟 race.protoss 和 race.terran 的值不一样就行。



Symbol 的用途就是如此：Symbol 可以创建一个独一无二的值（但并不是字符串）。

用 Symbol 来改写上面的 race：

var race = {
  protoss: Symbol(),
  terran: Symbol(),
  zerg: Symbol()
}

race.protoss !== race.terran // true
race.protoss !== race.zerg // true
你也可以给每个 Symbol 起一个名字：

var race = {
  protoss: Symbol('protoss'),
  terran: Symbol('terran'),
  zerg: Symbol('zerg')
}
不过这个名字跟 Symbol 的值并没有关系，你可以认为这个名字就是个注释。如下代码可以证明 Symbol 的名字与值无关：

var a1 = Symbol('a')
var a2 = Symbol('a')
a1 !== a2 // true
如果你觉得我说得还是太复杂了，看不懂，你可以记一句话：

Symbol 生成一个全局唯一的值。



以上，就是 Symbol 的简述。
#### undefined 和 null 都表示没有值，至于 JS 为什么有两个表示「没有值」的东西，可以从 JS 之父的 twitter 中知道当时他也挺纠结的：https://twitter.com/BrendanEich/status/333008305461006336
	•	（规范）如果一个变量没有被赋值，那么这个变量的值就是 undefiend
	•	（习俗）如果你想表示一个还没赋值的对象，就用 null。如果你想表示一个还没赋值的字符串/数字/布尔/symbol，就用 undefined（但是实际上你直接 var xxx 一下就行了，不用写 var xxx = undefined）
#### object
	•	object 就是上面几种基本类型（无序地）组合在一起
	•	object 里面可以有 object
	•	  var person = {
	•	      name: 'Frank', 
	•	      'child': {
	•	          name: 'Jack'
	•	      }, // 最后这个逗号可有可无
	•	  }
	•	object 的 key 一律是字符串，不存在其他类型的 key
	•	object[''] 是合法的
	•	object['key'] 可以写作 object.key
	•	注意 object.key 与 object[key] 不同
	•	delete object['key']
	•	'key' in object
#### typeof 操作符
xxx 的类型
string
number
boolean
symbol
undefined
null
object
function

typeof xxx

'string'
'number'
'boolean'
'symbol'
'undefined'
'object'
'object'
'function'
注意 function 并不是一个类型
| typeof xxx| typeof xxx | typeof xxx | typeof xxx | typeof xxx | typeof xxx | typeof xxx | 
| --- | --- | 
|string | number | boolean ｜symbol ｜undefined ｜null ｜object ｜function｜
|'string'| 'number' | 'boolean' ｜'symbol' ｜'undefined'｜'object'｜'object' ｜'function'｜
