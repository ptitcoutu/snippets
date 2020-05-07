# snippets

## Kotlin code to retrieve mongodb ObjectId from its internal definition in java ObjectId
```
fun main() {
    println(toHexString(toByteArray(
     randomValue2 = 1,
     randomValue1 = 2936647,
     counter = 10767217,
     timestamp = 1569090576
        )))
}
fun int3(x: Int): Byte {
 return (x shr 24).toByte()
}
fun int2(x: Int): Byte {
 return (x shr 16).toByte()
}
fun int1(x: Int): Byte {
 return (x shr 8).toByte()
}
fun int0(x: Int): Byte {
 return x.toByte()
}

fun toByteArray(timestamp: Int, randomValue1: Int, randomValue2: Int, counter: Int): Array<Byte> {
        return arrayOf<Byte>(
            int3(timestamp), 
            int2(timestamp),
			int1(timestamp),
			int0(timestamp),
            int2(randomValue1),
            int1(randomValue1),
            int0(randomValue1),
            int1(randomValue2),
            int0(randomValue2),
            int2(counter),
            int1(counter),
            int0(counter));
}

val HEX_CHARS = arrayOf(
            '0', '1', '2', '3', '4', '5', '6', '7',
            '8', '9', 'a', 'b', 'c', 'd', 'e', 'f');
fun toHexString(byteArray: Array<Byte>): String {
        val chars = Array<Char>(24) { _ -> ' ' }
        var i = 0
        for (b: Byte in byteArray) {
            val firstHexVal: Int = ((b.toInt() shr 4) and 0xF)
            val secondHexVal: Int = (b.toInt() and 0xF)
            chars[i++] = HEX_CHARS[firstHexVal];
            chars[i++] = HEX_CHARS[secondHexVal];
        }
        return chars.joinToString("");
}
```

