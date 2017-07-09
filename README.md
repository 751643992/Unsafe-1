# Unsafe
dummy jar of unsafe java apis for Android/Eclipse

# sun.misc.Unsafe
```java
final Field field = sun.misc.Unsafe.class.getDeclaredField("THE_ONE");
field.setAccessible(true);
sun.misc.Unsafe unsafe = (sun.misc.Unsafe)field.get(null);
```

# libcore.io.Memory
```java
public static void alignedCopy(long dst, long src, long length) {
	for (length /= 4; length > 0; --length, dst += 4, src += 4) {
		libcore.io.Memory.pokeInt(dst,
				libcore.io.Memory.peekInt(src, false), false);
	}
}
```