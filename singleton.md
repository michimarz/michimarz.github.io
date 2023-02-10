Let's always use enum to implement Singleton pattern. 

This is the recommended method, because it doesn't have problems with serialization or reflection. It 100% guarantees there is only one instance of the singleton present within the JVM.

```java
public enum Singleton {
    INSTANCE;
}
```

and the use it like this:
```java
SingletonEnum singleton = SingletonEnum.INSTANCE;
```

Look at the example in java sources. This is taken from Comparators class:
```java
enum NaturalOrderComparator implements Comparator<Comparable<Object>> {
	INSTANCE;
	
	@Override
	public int compare(Comparable<Object> c1, Comparable<Object> c2) {
		return c1.compareTo(c2);
	}
	
	@Override
	public Comparator<Comparable<Object>> reversed() {
		return Comparator.reverseOrder();
	}

}
```

And it's used here (taken from Comparator class):
```java
@SuppressWarnings("unchecked")
public static <T extends Comparable<? super T>> Comparator<T> naturalOrder() {
	return (Comparator<T>) Comparators.NaturalOrderComparator.INSTANCE;
}
```


