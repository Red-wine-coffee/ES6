# ES6
a.解构参数:
  function breakfast（dessert,drink,{location,restaurant}={}）{
    console.log(dessert,drink,location,restaurant);
  }
  breakfast('甜甜圈','牛奶',{location:'长沙',restaurant:'巴黎甜点'});
b.函数名称：name
  function breakfast(){};//函数声明的方式创建函数
  console.log(breakfast.name) //breakfast
  let breakfast = function(); //匿名函数赋值
  console.log(breakfast.name) //breakfast
  let breakfast = function superBreakfast(); //函数声明之后赋值优先级更高 
  console.log(breakfast.name) //superBreakfast;
c.箭头函数：
  let breakfast = dessert => dessert;
  function breakfast(dessert){return dessert };
      let breakfast = (dessert,drink)=>{return dessert + drink};
  function breakfast(dessert,drink){return dessert + drink};
d.对象赋值：
  let breakfast = {dessert:"cake",drink:"milk"};
  let breakfast2 = {};//只能为对象其他无法赋值
  Object.assign(breakfast,breakfast2);
  console.log(breakfast2)//{dessert:"cake",drink:"milk"}
e.数组：
    let arr = [1, 2, 3, 'cc', 5, 1, 9];
    	console.log(arr.find((value, keys, arr) => {
    	    return value > 2;
    	}))//3
    const list = [{'name':'1',index:1},{'name':'2'},{'name':'1'}]
    let list2 = list.find(i=>i.name==='1')
    let list3 = list.filter(i=>i.name==='1')
    console.log(list); [ { name: '1', index: 1 }, { name: '2' }, { name: '1' } ]
    console.log(list2); { name: '1', index: 1 }
    console.log(list3);[ { name: '1', index: 1 }, { name: '1' } ]
    find 返回的是一个对象，filter 返回的是一个数组，都不会改变原数组
f.classes：
    class breakfast {
      constructor(food){ //可将初始化的数据放进去
        this.food = food;
      }
      cook(){
        console.log(this.food);
      }
    }
    let wanhao = new breakfast("cake");
    wanhao.cook()//cake
g.继承-extends:
    class Person{
      constructor(name,birthday){
        this.name = name ;
        this.birthday = birthday;
      }
      intro(){
        return `${name},${birthday}`;
      }
    }
    class Chef extends Person{
      constructor(name , birthday){
        super(name,birthday);
      }
    }
    let wanhao = new Chef('wanghao','1886-05-12');
    console.log(wanhao.intro());//'wanghao','1886-05-12'
h.Set:(对象或数组里面的数据不能是重复的)
    let arr = [1, 2, 3, 'cc', 5, 1, 9,2,3];
    let arr2 = [];
   	let desserts = new Set(arr);
    desserts.forEach(item => {
      arr2.push(item);
    })
    console.log(arr2);
I.数组的拷贝：
    1.let arr = [1,2,3];
      let arr2 = JSON.parse(JSON.stringify(arr));
    2.let arr2 = [...arr];
