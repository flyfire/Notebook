extract method 抽取方法
pull up method 将方法推入超类中
form template method 将模板方法放入超类中，子类来提供具体实现
substitute algorithm 替换函数实现，将函数本体替换为另一个算法。
extract class 将一个类中聚集的不太相关的数据和操作移到另外的类中 Person, TelephoneNumber
replace temp with query 将临时变量的计算放入函数中，这样在类的其他地方也能访问到
introduce parameter object 以一个对象取代函数参数，当你把这些参数组织到一起之后，往往很快可以发现一些可被移动到新建类的行为
replace method with method object 以函数对象取代函数。有一个大型函数，其中对局部变量的使用使你无法采用extract method，可以将这个函数放进一个单独对象中，如此一来局部变量就成了对象内的字段，然后你可以在同一个对象中将这个大型函数分解为多个小型函数。
decompose conditional 分解条件表达式 可以将复杂的条件逻辑分解为多个独立函数，根据每个小块代码的用途为分解而得的新函数命名，并将原函数中对应的代码改为调用新建函数，从而更清楚地表达自己的意图。对于条件逻辑，将每个分支条件分解成新函数还可以给你带来更多好处，可以突出条件逻辑，更清楚地表明每个分支的作用，并且突出每个分支的原因。
replace nested conditional with guard clauses 以卫语句取代嵌套条件表达式。卫语句要不就从函数中返回，要不就抛出一个异常。常常可以将条件表达式反转，从而实现replace nested conditional with guard clauses
extract subclass 提炼子类，类中的某些特性只被某些而非全部实例用到，新建一个子类，将上面所说的那一部分特性移到子类中。
preserve whole object 保持对象完整 你从某个对象中取出若干值，将它们作为某一次函数调用时的参数，改为传递整个对象。
replace type code with subclasses 以子类取代类型码
decompose conditional 分解条件表达式，从if，then，else三个段落中分别提炼出独立函数，如果发现嵌套的条件逻辑，通常要先观察是否可以使用replace nested conditional with guard clauses，如果不行，才开始分解其中的每个条件
consolidate conditional expression 合并条件表达式 有时候你会发现这样一串条件检查，检查条件各不相同，最终行为却一致。如果发现这种情况，就应该使用“逻辑或”和“逻辑与”将它们合并为一个条件表达式。
extract class将几个变量一起提炼至新类内。提炼时应该选择类内彼此相关的变量，将它们放在一起。
duplicate observed data
replace parameter with methods 以函数取代参数，对象调用某个函数，并将所得结果作为参数，传递给另一个函数，而接受该参数的函数本身也能够调用前一个函数。让参数接受者去除该项参数，直接调用前一个函数。如果函数可以通过其他途径获得参数值，那么它就不应该通过参数取得该值。过长的参数列会增加程序阅读者的理解难度，因此我们应该尽可能缩短参数列的长度。
introduce parameter object引入参数对象 某些参数总是很自然地同时出现，以一个对象取代这些参数。DateRange