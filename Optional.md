## 1.  Optional
Optional<T>是在java.util包下的一个用于代替null的一个工具类
![[1691397223373.png]]
## 2. Optional的构造方法
JDK 提供三个静态方法来构造一个Optional：

- Optional.of(T value)，该方法通过一个非 null 的 value 来构造一个 Optional，返回的 Optional 包含了 value 这个值。对于该方法，传入的参数一定不能为 null，否则便会抛出 NullPointerException。
|
- Optional.ofNullable(T value)，该方法和 of 方法的区别在于，传入的参数可以为 null , 但是前面 javadoc 不是说 Optional 只能包含非 null 值吗？原来该方法会判断传入的参数是否为 null，如果为 null 的话，返回的就是 Optional.empty()。  
|
- Optional.empty()，该方法用来构造一个空的 Optional，即该 Optional 中不包含值,其实底层实现还是 如果 Optional 中的 value 为 null 则该 Optional 为不包含值的状态，然后在 API 层面将 Optional 表现的不能包含 null 值，使得 Optional 只存在 包含值 和 不包含值 两种状态。
|
- ![[1691397730267.png]]
## 3. 相关方法
- 