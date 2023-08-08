## 1.  Optional
`Optional<T>`是在`java.util`包下的一个用于代替null的一个工具类
![[1691397223373.png]]
## 2. Optional的构造方法
JDK 提供三个静态方法来构造一个Optional：

- `Optional.of(T value)`，该方法通过一个非 null 的 value 来构造一个 Optional，返回的 Optional 包含了 value 这个值。对于该方法，传入的参数一定不能为 null，否则便会抛出 NullPointerException。
|
- `Optional.ofNullable(T value)`，该方法和 of 方法的区别在于，传入的参数可以为 null , 但是前面 javadoc 不是说 Optional 只能包含非 null 值吗？原来该方法会判断传入的参数是否为 null，如果为 null 的话，返回的就是 Optional.empty()。  
|
- `Optional.empty()`，该方法用来构造一个空的 Optional，即该 Optional 中不包含值,其实底层实现还是 如果 Optional 中的 value 为 null 则该 Optional 为不包含值的状态，然后在 API 层面将 Optional 表现的不能包含 null 值，使得 Optional 只存在 包含值 和 不包含值 两种状态。
|
- ![[1691397730267.png]]
## 3. 相关方法
- ### ifPresent
![[Pasted image 20230807164643.png]]
例:
`
Optional<User> user = Optional.ofNullable(getUserById(id));
user.ifPresent(System::out.println);
`
- ### orElse
![[1691398348096 1.png]]
Optional 中有值则将其返回，否则返回 orElse 方法传入的参数。
例:
`
Optional<Insurance> objectOptional = Optional.ofNullable(null);
objectOptional.orElse(new Insurance());
`
- ### orElseGet
![[1691398627261 1.png]]
orElseGet 与 orElse 方法的区别在于，orElseGet 方法传入的参数为一个 Supplier 接口的实现 —— 当 Optional 中有值的时候，返回值；当 Optional 中没有值的时候，返回从该 Supplier 获得的值。
`
Optional<Insurance> objectOptional = Optional.ofNullable(null);
objectOptional.orElseGet(Insurance::new);
`
- ## orElseThrow
![[Pasted image 20230807170018.png]]
orElseThrow 与 orElse 方法的区别在于，orElseThrow 方法当 Optional 中有值的时候，返回值；没有值的时候会抛出异常，抛出的异常由传入的 exceptionSupplier 提供。
`
Optional<Insurance> objectOptional = Optional.ofNullable(null);
objectOptional.orElseThrow(() -> new RuntimeException("Not have reference"));
`
- ## map
![[1691456132012.png]]
当前 Optional 为 Optional.empty，则依旧返回 Optional.empty；否则返回一个新的 Optional，该 Optional 包含的是：函数 mapper 在以 value 作为输入时的输出值。
`
objectOptional.map(Insurance::getName)
`
- ## flatMap
![[1691456435269.png]]
flatMap 方法与 map 方法的区别在于，map 方法参数中的函数 mapper 输出的是值，然后 map 方法会使用 Optional.ofNullable 将其包装为 Optional；而 flatMap 要求参数中的函数 mapper 输出的就是 Optional
`
Optional<String> username = Optional
        .ofNullable(getUserById(id))
        .flatMap(user -> Optional.of(user.getUsername()))
        .flatMap(name -> Optional.of(name.toLowerCase()));
`
- ## filter
![[1691456688227.png]]
filter 方法接受一个 Predicate 来对 Optional 中包含的值进行过滤，如果包含的值满足条件，那么还是返回这个 Optional；否则返回 Optional.empty。
`
Optional<String> username = Optional
        .ofNullable(getUserById(id))
        .filter(user -> user.getId() < 10)
        .map(user -> user.getUsername());
`