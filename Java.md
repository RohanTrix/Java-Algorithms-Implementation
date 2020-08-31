# 14. Java

## 14.1 Math.random

```java
public class dice1{
    public int roller(){
        return ((int)(1+Math.random()*6));  
        // Math.random() returns a double value of 0 to less than 1
        // So Math.random()*6 creates value like 1.23 ,3,24, 5,343 ,0.0 
        // we need value from 1 to 6 integer type
        // so that’s why we are casting into int
        // but why plus one
        /* as you can see 0.0 int value 0 we don’t need that and also      highest value of Math.random()*6 */
        /* is 0.99*6=5.94 so if we int it then we get 5 so that’s why we are adding one so */
        // Math.random()*6 where 0.0*6 = 0+1 = 1 then int it we get 1
        // Math.random()*6 where 0.99*6 = 5.94+1 = 6.94 then int it we get 6
        // one question will arise to your mind that why not
        // Math.random()*7 yes that will solve one problem  
        // Math.random()*7 where 0.99*7 = 6.94 then int it we get 6
        // not the 0.0*7 = 0 problem
        // so in generally we have a start point and an end point 
        // a = the first number in your range
        // b = the last number in your range
        // r = (b - a + 1) is the number of terms in your range
        // (range computed by largest value - smallest value + 1
        // so for generating numbers between 13 to 19 excluding
        // a = 14 and b = 18 so r = (18-14+1) = 5  
        // return ((int) (14+Math.random ()*5));  
    }  
}
```

## 14.2 Big Integer

```
import java.math.BigInteger; // have to include

A + B = C              -->  C = A.add(B);
A - B = C              -->  C = A.subtract(B);
A * B = C              -->  C = A.multiply(B);
A / B = C              -->  C = A.divide(B);
A % B = C              -->  C = A.remainder(B);
A % B = C where C > 0  -->  C = A.mod(B);
A / B = Q & A % B = R  -->  C = A.divideAndRemainder(B);
// return an array of size 2, which 1st index keeps the                   quotient & 2nd index keeps the remainder 
// (Q = C [0], R = C [1])

A ^ b = C              -->  C = A.pow(B); 
// Returns n1(BInt) to the power n2(Int)
abs(A) = C             -->  C = A.abs();
-(A) = C               -->  C = A.negate();
   
gcd(A,B) = C           -->  C = A.gcd(B);
(A ^ B) % M            -->  C = A.modPow(B,M);
C = inverse of A mod M -->  C = A.modInverse(M);

max(A,B) = C           -->  C = A.max(B);
min(A,B) = C           -->  C = A.min(B);


Bit Operations
------------------
~A = C       (NOT)     -->  C = A.not();
A & B = C    (AND)     -->  C = A.and(B);
A | B = C    (OR)      -->  C = A.or(B);
A ^ B = C    (XOR)     -->  C = A.xor(B);
A & ~B = C   (ANDNOT)  -->  C = A.andNot(B);
A << n = C   (LSHIFT)  -->  C = A.shiftLeft(n);
A >> n = C   (RSHIFT)  -->  C = A.shiftRight(n);

Clear n'th bit of A    -->  C = A.clearBit(n);
Set   n'th bit of A    -->  C = A.setBit(n);
Flip  n'th bit of A    -->  C = A.flipBit(n);
Test  n'th bit of A    -->  C = A.testBit(n);
   
Bitcount of A = n      -->  n = A.bitCount();
Bitlength of A = n     -->  n = A.bitLength();
Lowest set bit of A    -->  n = A.getLowestSetBit();     
       
BigInteger val1 = BigInteger.ZERO;    // val1 = 0 
BigInteger val2 = BigInteger.ONE;     // val2 = 1
BigInteger val3 = BigInteger.TEN;     // val3 = 10

A < 0                  -->  A.signum() == -1;
A == 0                 -->  A.signum() ==  0;
A > 0                  -->  A.signum() ==  1;


/* compareTo */
if(num1.compareTo(num2) > 0)   // num1 > num2 return +1
if(num1.compareTo(num2) < 0)   // num1 < num2 return -1  
if(num1.compareTo(num2) == 0)  // num1 == num2 return 0
if(num1.compareTo(num2) >= 0)  // num1 >= num2
if(num1.compareTo(num2) <= 0)  // num2 <= num1
   
Conversion:
-----------
double                 -->  A.doubleValue();
float                  -->  A.floatValue();
int                    -->  A.intValue();
long                   -->  A.longValue();
byte[]                 -->  A.toByteArray();
String                 -->  A.toString();
String (base b)        -->  A.toString(b);   
// converts base 10 to desire base  
BigInteger val = new BigInteger("1111", b); // b = 2
// returns values in decimal, 15
// 2 ≤b ≤ 36
  
BigInteger num3 = new BigInteger ("111111"); 
String s = "111111";  
BigInteger num3 = new BigInteger (s);
BigInteger num4 = new BigInteger ("111111");   
BigInteger num5 = BigInteger.valueOf(11111); //BigInteger.valueOf(long val)

BigInteger p = BigInteger.valueOf(5)
BigInteger q = a.nextProbablePrime(); // here q = 7

// Returns the first integer greater than this BigInteger that is probably prime. The probability that the number returned by this method is composite does not exceed 2-100. This method will never skip over a prime when searching: if it returns p, there is no prime q such that this < q < p
```

## 14.3 Big Decimal

```java
import java.math.BigDecimal; // have to include

A + B = C              -->  C = A.add(B);
A - B = C              -->  C = A.subtract(B);
A * B = C              -->  C = A.multiply(B);
A % B = C              -->  C = A.remainder(B);
A / B = C              -->  C = A.divide(B, roundingMode);
// Where C.scale() == A.scale()
A / B = C        -->  C = A.divide(B, scale, roundingMode);
// Where C.scale() == scale

abs(A) = C             -->  C = A.abs();
-(A) = C               -->  C = A.negate();
   
max(A,B) = C           -->  C = A.max(B);
min(A,B) = C           -->  C = A.min(B);

            
            
BigDecimal val1 = BigDecimal.ZERO;     // val1 = 0 
BigDecimal val2 = BigDecimal.ONE;      // val2 = 1
BigDecimal val3 = BigDecimal.TEN;      // val3 = 10
            
/* compareTo */
if(num1.compareTo(num2) > 0)      // num1 > num2  return +1
if(num1.compareTo(num2) < 0)      // num1 < num2  return -1  
if(num1.compareTo(num2) == 0)     // num1 == num2  return -0
if(num1.compareTo(num2) >= 0)     // num1 => num2
if(num1.compareTo(num2) <= 0)     // num2 >= num1

BigDecimal num3 = new BigDecimal ("111111.111"); 
String s = "111111";  
BigDecimal num3 = new BigDecimal (s);
BigDecimal num4 = new BigDecimal ("111111.111");      
BigDecimal num5 = BigDecimal.valueOf(11111); 

A < 0                  -->  A.signum() == -1;
A == 0                 -->  A.signum() ==  0;
A > 0                  -->  A.signum() ==  1;

Conversion:
-----------
double                 -->  A.doubleValue();
float                  -->  A.floatValue();
int                    -->  A.intValue();
long                   -->  A.longValue();
String                 -->  A.toString();
BigInteger             -->  A.toBigInteger();
BigInteger             -->  A.unscaledValue();

 
Scale Manipulation Operations
-----------------------------
movePointLeft(int n)  -->  Moves decimal point right or                      left depending on value of n.
movePointRight(int n) -->  Opposite of Left.
int scale()           -->  Returns current scale.
setScale(scale)       -->  Used to increase precision.
setScale(scale, roundingMode)  -->  Round to scale digits after decimal point.

BigDecimal n1 = sc.nextBigDecimal();              
int n2 = sc.nextInt(); 
// Returns n1(BDec) to the power n2(Int)
BigDecimal bi2 = n1.pow(n2);

String s = ans.toPlainString(); 
// bigdecimal value without using the exponent field

BigDecimal ans = ans.stripTrailingZeros();
// remove all the trailing zeros
// input 123.343544500000000
// output 123.3435445
// special case:
// input 12.0000000   
// output 12.00000000 /* have to check manually */ /*don’t use*/
```

## 14.4 String

```java
// For giving the value a to z 1, 2, 3 to 26 and A to Z 27, 28, 29 to 52

for(int i = 0; i < line.length(); ++i) {
    if(line.charAt(i) >= 'a' && line.charAt(i) <= 'z')
       sum += line.charAt(i) - 'a' + 1; 
    // sum += line.charAt(i) - 96;
    else if(line.charAt(i) >= 'A' && line.charAt(i) <= 'Z')
       sum +=  line.charAt(i) - 'A' + 27;
    // sum += line.charAt(i) – 39;
} 
```

```java
// For giving the value 1 to 9 1, 2, 3 to 9 

for(int i = 0; i < s.length(); ++i){
    if(Character.isDigit(s.charAt(i))) {
         sum += s.charAt(i) - '0';
      // sum += s.charAt(i) - 48;
    }
}
```

```
// ASCII value of 0 to 9 is 48 to 57
‘0’ = 48 – 48 = 0
‘1’ = 49 – 48 = 1
‘2’ = 50 – 48 = 2
‘3’ = 51 – 49 = 3
‘4’ = 52 - 48 = 4
‘5’ = 53 – 48 = 5
‘6’ = 54 – 48 = 6
‘7’ = 55 – 48 = 7
‘8’ = 56 – 48 = 8
‘9’ = 57 – 48 = 9

Digit value of x
ans = ‘x’ – ‘0’
ASCII value of x – ASCII value of zero 
```

```java
/* Letter Addition */
abcd + ABCD = 2 × (a + b + c + d) + (4 × 32)

/* Letter Subtraction */
abcd – ABCD = 4 × 32

/* String Concatenation */
String s = “tai”;
String d = “naki”;
String c = s + d; or String c = s.concat(d);

/* String Split */ /* try to use StringTokenizer bcz it’s slow */
String s = sc.nextLine();
String [] string_ar = s.split (" "); 
for (int c = 0 ; c < string_ar.length ; c++)
  System.out.println (string_ar[c]);

/* char Split */
String s = sc.nextLine() ;
char [] char_ar = new char [s.length()] ; 
s.getChars (0, s.length(), char_ar, 0) ; 
for (int c = 0 ; c < char_ar.length ; c++)
  System. out .println (char_ar [c]) ;

// Alternate
char charArray [] = s.toCharArray();
```

```java
/* substring */
s.substring (start char index, end char index + 1);

String s = "apple";         
// s = s.substring (0, 2+1); 
// returns "app"

// a	p	p	l	e
// 0	1	2	3	4


s.substring (start char index);
// String s = "unhappy";         
// s.substring(2) 

// returns "happy" 

// u	n	h	a	p	p	y
// 0	1	2	3	4	5	6

/* indexOf */

s.indexOf(‘a’);

// the index of the first occurrence of the character in the character sequence represented by this object, or -1 if the character does not occur.

/* lastIndexOf */

s.lastIndexOf(‘c’);

// Returns the index within this string of the last occurrence of the specified character

/* indexOf */
s.indexOf(“tai”);
// Returns the index within this string of the first occurrence of the specified substring
// String s = "abcd sde qwe aaa";
// System.out.println( s.indexOf("aaa"));
// 13 

/* lastIndexOf */

lastIndexOf(“tai”); 
// Returns the index within this string of the rightmost occurrence of the specified substring

/* replace */
s.replace(oldChar, newChar);

// a string derived from this string by replacing every occurrence of oldChar with newChar.

// "mesquite in your cellar".replace('e', 'o');
   returns "mosquito in your collar"

/* trim */
s.trim();
// Returns a copy of the string, with leading and trailing whitespace omitted.

/* startsWith */

s.startsWith(String prefix, int toffset)

// Tests if the substring of this string beginning at the specified index starts with the specified prefix. 
s.startsWith(String prefix)

Parameters:
prefix - the prefix.
toffset - where to begin looking in this string. 
// true if the character sequence represented by the argument is a prefix of the character sequence represented by this string; false otherwise

/* endsWith */

s.endsWith(String suffix)

// Tests if this string ends with the specified suffix

/* toLowerCase() */
line.toLowerCase();

/* toUpperCase() */
line.toUpperCase();

/* regionMatches */

s.regionMatches(int toffset, String other, int ooffset, int len)

// Tests if two string regions are equal. 
s.regionMatches(boolean ignoreCase,int toffset,String other,int ooffset, int len)

Parameters:
ignoreCase - if true, ignore case when comparing characters.
toffset - the starting offset of the subregion in this string.
other - the string argument.
ooffset - the starting offset of the subregion in the string argument.
len - the number of characters to compare. 

// true if the specified subregion of this string matches the specified subregion of the string argument
```

<img width="581" alt="Screen Shot 2020-04-07 at 4 41 58 pm" src="https://user-images.githubusercontent.com/1612112/78637951-c623b580-78ee-11ea-9091-4e9ce1227df8.png">

```java
s.regionMatches(true, 0, desh, 0, 4);

/* replaceFirst */

s.replaceFirst("aaa", "D")

// Replaces only first occurrences of given String with new one and returns   new String object

/* replaceAll */

s.replaceAll("Re", "Ra")

// Replaces all occurrences of given String with new one and returns new String object


/* contains */
line.contains("A")
// Returns true if and only if this string contains the specified sequence of char values


/* String Wrap Around */
val = ord (i) + shift
if val > 90 and i.isupper():
    val = val % 91 + 65
if val > 122 and i.islower():
    val = val % 123 + 97
```

## 14.5 StringBuffer

```java
StringBuffer rev = new StringBuffer("Hello"); 
rev.reverse();
// this character sequence to be replaced by the reverse of the sequence 
rev.toString();
// Returns a string representing the data in this sequence 
rev.delete(int start, int end) 
// Removes the characters in a substring of this sequence 
// start - The beginning index, inclusive
// end - The ending index, exclusive
rev.deleteCharAt(int index);

// Removes the char at the specified position in this sequence. This sequence is shortened by one char
```

## 14.6 StringTokenizer

```java
StringTokenizer sT = new StringTokenizer("Hello");
// Constructs a string tokenizer for the specified string. The tokenizer uses the default delimiter set, which is " \t\n\r\f": the space character, the tab character, the newline character, the carriage-return character, and the form-feed character. Delimiter characters themselves will not be treated as tokens

// don’t forget to include the space
StringTokenizer sT = new StringTokenizer(s," 1234567890`-=~!@#$%^&*()_+[]\\;',./{}|:\"<>?\t\n\r");
// 46 character’s
 
while(sT.hasMoreTokens())
    sT.nextToken();

sT.countTokens();

// calculates the number of times that this tokenizer's nextToken method can be called before it generates an exception
```

## 14.7 Character

```java
Character.isDigit(char ch)
// returns true if the char is a digit

Character.digit(char ch, int radix) 
// Character.digit(number.charAt(i), 10);

// Returns the numeric value of the character ch in the specified radix
```

## 14.8 Tree Set

```java
/* This implementation provides guaranteed log(n) time cost for the basic operations (add, remove and contains).Constructs a new, empty set, sorted according to the elements' natural order. No duplicate value is stored */  
 
TreeSet <Integer> i = new TreeSet <Integer> ();
TreeSet <Long> l = new TreeSet <Long> ();
TreeSet <Double> d = new TreeSet <Double> ();
TreeSet <BigInteger> b = new TreeSet <BigInteger> ();
TreeSet <String> s = new TreeSet <String> ();
TreeSet <Character> c = new TreeSet <Character> ();

Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <BigInteger> itB = b.iterator();
Iterator <String> itS = s.iterator();
Iterator <Character> itC = c.iterator();

i.clear(); 
// Removes all of the elements from this set
i.add(17); 
// Adds the specified element to this set if it is not already present
i.size(); 
// Returns the number of elements in this set (its cardinality)
i.contains(17); 
// Returns true if this set contains the specified element
i.first(); 
// Returns the first (lowest) element currently in this sorted set
i.last(); 

// Returns the last (highest) element currently in this sorted set
i.remove(17); 
// Removes the specified element from this set if it is present
i.isEmpty(); 
// Returns true if this set contains no elements
        
while(itI.hasNext())
    System.out.println(itI.next()); 

// i = {78, 69, 80, 77, 82, 75, 81}
// the internal content of i MAY be something like this
// the keys are values (integers)!
//                 (78) 
//         (75)            (81)   
//     (69)    (77)    (80)    (82)

i.headSet(77);  
// returns [69, 75] (these two are before 77 in the inorder traversal of this BST) and if there are no values it returns [] i.tailSet(77);  
// returns [77, 78, 80, 81, 82] (these five are equal or after 77 in the inorder traversal of this BST) and if there are no values it returns []
```

## 14.9 Hash Set

```java
/* A HashSet is a collection set that neither allows duplicate elements nor order or position its elements.*/

HashSet <Integer> i = new HashSet <Integer> ();
HashSet <Long> l = new HashSet <Long> ();
HashSet <Double> d = new HashSet <Double> ();
HashSet <String> s = new HashSet <String> ();
HashSet <Character> c = new HashSet <Character> ();
         
Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <String> itS = s.iterator();
Iterator <Character> itC = c.iterator();
        
i.add(17);
// Adds the specified element to this set if it is not already present
i.clear();
// Removes all of the elements from this set
i.contains(17); 
// Returns true if this set contains the specified element
i.size();
// Returns the number of elements in this set (its cardinality)
i.remove(17); 
// Removes the specified element from this set if it is present
i.isEmpty();
// Returns true if this set contains no elements

s.add("1");
s.add("1");
s.add("2");

while(itS.hasNext()){
    System.out.println(itS.next());
}

String joined = String.join(",", s);
```

## 14.10 Tree Map

```java
/* This implementation (Red-black tree) provides guaranteed log(n) time cost for the containsKey, get, put and remove operations. It is a sorted map */

TreeMap<Integer , Integer> i = new TreeMap<Integer , Integer> ();
TreeMap <Long , Long> l = new TreeMap <Long , Long> ();
TreeMap <Double , Double> d = new TreeMap <Double , Double> ();
TreeMap <String , String> s = new TreeMap <String , String> ();
              
s.clear();
// Removes all of the mappings from this map
s.size();
// Returns the number of key-value mappings in this map
s.isEmpty();
// Returns true if this map contains no key-value mappings
s.remove("jhon");
// Removes the mapping for this key from this TreeMap if present
s.put(key, value); 
// Associates the specified value with the specified key in this map 
s.get("ananda");
// Returns the value to which the specified key is mapped, or null if this map contains no mapping for the key
s.containsKey("ananda");
// Returns true if this map contains a mapping for the specified key
s.keySet();
// Returns a Set view of the keys contained in this map 
s.values();
// Returns a Collection view of the values contained in this map

s.firstKey(); 
// Returns the first (lowest) key currently in this map
s.lastKey();
// Returns the last (highest) key currently in this map.
s.higherKey(key);  
// Returns the least key strictly greater than the given key, or null if  there is no such key.
s.lowerKey(key);  
// Returns the greatest key strictly less than the given key, or null if        there is no such key.
s.floorKey(key);
// Returns the greatest key less than or equal to the given key, or null if there is no such key.
s.ceilingKey(key); 
// Returns the least key greater than or equal to the given key, or null if there is no such key.
```

```java
// 3
// Spain
// England
// Spain

count = s.get(s);
if (count == null)
    s.put(s, 1);
else
    s.put(s, ++count);

s.keySet();
// [England, Spain] 

s.values();
// [1, 2] 

val = sc.nextInt();
if(frq.containsKey(val) == false)
     frq.put(val, 1);
else{
      count = frq.remove(val);
      frq.put(val, count + 1);
}
```

## 14.11 Hash Table

```java
Hashtable<Integer, Integer> i = new Hashtable<Integer, Integer>();  
Hashtable<Long, Long> l = new Hashtable<Long, Long>();  
Hashtable<Double, Double> d = new Hashtable<Double, Double>();  
Hashtable<String, String> s = new Hashtable<String, String>();  
                
s.clear();
// Clears this hashtable so that it contains no keys.
s.size();
// Returns the number of keys in this hashtable.
s.isEmpty();
// Tests if this hashtable maps no keys to values.
s.remove("jhon");
// Removes the key (and its corresponding value) from this hashtable.
s.put(key, value); 
// Maps the specified key to the specified value in this hashtable.
s.get("ananda");
// Returns the value to which the specified key is mapped, or null if this map contains no mapping for the key.
s.containsKey("ananda");
// Tests if the specified object is a key in this hashtable.
s.keySet();
// Returns a Set view of the keys contained in this map.
s.values();
// Returns a Collection view of the values contained in this map.

// sorting a HashTable
  Vector<String> v = new Vector<String>(tree.keySet()); 
  Collections.sort(v);
       for(int j = 0; j < v.size(); ++j) {
           String element = v.elementAt(j);
            System.out.printf("%s %.4f\n",element, tree.get(element));
       }
// or
Vector v = new Vector<String>(tree.keySet()); 
Collections.sort(v);
Iterator <String> it = v.iterator();
        while (it.hasNext()) {
               String element = it.next();
               System.out.printf("%s %.4f\n",element, tree.get(element));
        }
```

## 14.12 Arrays

```java
byte[]a    
char[]a    
double[]a  
float[]a   
int[]a     
long[]a    
Object[]a 
short[]a  
```

```
Array Type   Default Values
byte[]a      -> 0
char[]a      -> 0
double[]a    -> 0.0
float[]a     -> 0.0
int[]a       -> 0
long[]a      -> 0
Object[]a    -> null
short[]a     -> 0
boolean[]a   -> false
String[]a    -> null
char[]a      -> 
```

```java

Arrays.binarySearch(double[] a, int fromIndex, int toIndex, double key)

// a - the array to be searched
// fromIndex - the index of the first element (inclusive) to be searched
// toIndex - the index of the last element (exclusive) to be searched
// key - the value to be searched for 

Arrays.binarySearch(byte[] a, byte key)

// a - the array to be searched
// key - the value to be searched for 

/* If the array contains multiple elements with the specified value, 
   there is no guarantee which one will be found. The return value
   will be >= 0 if and only if the key is found. If not found then 
   (-(insertion point) - 1). The insertion point is defined as the 
   point at which the key would be inserted into the array */

 // so it can be used as a lower bound like 

 int ar [] = {1, 5, 10, 10, 10, 20};
 // 0, 1,  2,  3,  4,  5

 int res = Arrays.binarySearch(ar,25);
 res = -7 // also we can write ( - (6) - 1)
 ans = Math.abs (res + 1) = 6

 /* IN FACT NO */ /* there is one case that it would not work */

int ar [] = {1, 5, 10, 10, 10, 10, 10, 10, 10, 10, 10, 20};
// 0, 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11

// which values are in the array the lower bound will fail because java is not guarantee you that it will return the first occurrence index. It will give you any of the indexes from 2 to 10 for key = 10

sort(a, fromIndex, toIndex)

/* Sorts the specified range of the specified array of doubles into
ascending numerical order. The range to be sorted extends from 
index fromIndex, inclusive, to index toIndex, exclusive. 
(If fromIndex==toIndex, the range to be sorted is empty.) 

a - the array to be sorted
fromIndex - the index of the first element (inclusive) to be sorted
toIndex - the index of the last element (exclusive) to be sorted */
```

## 14.13 Vector

```java
// 1D
Vector<Integer> i = new Vector<Integer>();
Vector<Long> l = new Vector<Long>(); 
Vector<Double> d = new Vector<Double>(); 
Vector<String> s = new Vector<String>(); 
Vector<BigInteger> b = new Vector<BigInteger>();
Vector<Byte> b = new Vector<Byte>();
        
i.add(10);
// appends the specified element to the end of this Vector
i.add(5,20);
// Inserts the specified element at the specified position in this Vector
i.set(5, 100);
// Replaces the element at the specified position in this Vector with the specified element
i.get(5);
// Returns the element at the specified position in this Vector
i.size();
// Returns the number of components in this vector
i.clear();
// Removes all of the elements from this Vector 
/* Remember Collections.fill() Problem */
i. insertElementAt(5, pos);
// pos = 0, insert at front

public static void showVector(Vector<Integer> v) {
    for(int i = 0; i < v.size(); ++i)
        System.out.println(v.elementAt(i));
}

Vector<Integer> v = new Vector<Integer> (Collections.nCopies (5, 5)); 
// initial size (5) and initial value {5, 5, 5, 5, 5} 
```

## 14.14 

```java
List<Integer> nums = new ArrayList<Integer>();

nums.add("1");
nums.add("2");
nums.add("3");
nums.add("4");
System.out.println(cars);


// convert ArrayList to int array
int[] array = list.stream().mapToInt(i->i).toArray();
```

## 14.15 Array Deque

```java

/*Double Ended Queue support adding and removing elements from both ends*/

ArrayDeque<Integer> i = new ArrayDeque<Integer>();
ArrayDeque<Long> l = new ArrayDeque<Long>();
ArrayDeque<Double> d = new ArrayDeque<Double>();
ArrayDeque<String> s = new ArrayDeque<String>();

Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <String> itS = s.iterator();

Iterator <Integer> itI = i.descendingIterator();
Iterator <Long> itL = l.descendingIterator ();
Iterator <Double> itD = d.descendingIterator ();
Iterator <String> itS = s.descendingIterator ();

Q1.clear(); 
// Removes all of the elements from this deque
Q1.add(17); 
// Inserts the specified element at the end of this deque
Q1.size(); 
// Returns the number of elements in this deque
Q1.remove();
// Retrieves and removes the head of the queue represented by this deque
Q1.remove(17); 
// Removes a single instance of the specified element from this deque
Q1.isEmpty();

// Returns true if this deque contains no elements
Q1.addFirst(17);
// Inserts the specified element at the front of this deque
Q1.addLast(17);
// Inserts the specified element at the end of this deque
Q1.removeFirst(17);
// Retrieves and removes the first element of this deque
Q1.removeLast(17);
// Retrieves and removes the last element of this deque
Q1.getFirst();
// Retrieves, but does not remove, the first element of this deque
Q1.getLast();
//Retrieves, but does not remove, the last element of this deque

while(itI.hasNext())
 	System.out.println(itI.next()); 
```

## 14.16 Stack

```java
/*The Stack class represents a last-in-first-out (LIFO) stack of objects*/

Stack <Integer> s1 = new Stack <Integer>();
Stack <Long> s2 = new Stack <Long>();
Stack <Double> s3 = new Stack <Double>();   
Stack <String> s4 = new Stack <String>();
Stack<Character> s = new Stack<Character>();

s.push();
// Pushes an item onto the top of this stack
s.pop();
// Removes the object at the top of this stack and returns that object as the value of this function
s.peek();
// Looks at the object at the top of this stack without removing it from the stack
s.empty();
// Tests if this stack is empty
s.clear();
// Remove all elements from the collection 

s.push('a');
s.push('b');
s.push('c');
// c <- top of the stack [TOS]
// b
// a

for(Character c: s)
    System.out.println(c);
```

## 14.17 Queue

```java
/* The Queue class represents a first-in-first-out (FIFO) stack of objects */

Queue<Integer> i = new LinkedList<Integer>();
Queue<Long> l = new LinkedList<Long>();
Queue<Double> d = new LinkedList<Double>();
Queue<String> s = new LinkedList<String>();
Queue<Character> c = new LinkedList<Character>(); 

Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <String> itS = s.iterator();
Iterator <Character> itC = c.iterator();
  
i.offer(10);
// Inserts the specified element into this queue, if possible
i.peek();
// Retrieves, but does not remove, the head of this queue, returning null if this queue is empty
i.poll();
// Retrieves and removes the head of this queue, or null if this queue is empty
i.remove();
// Retrieves and removes the head of this queue
i.isEmpty();
// Tests if this queue is empty
i.clear();
// Remove all elements from the collection 

while(itI.hasNext())
 	 System.out.println(itI.next()); 

s.offer(10);
s.offer(20);
s.offer(30);
// 10 <- Front
// 20
// 30
```

## 14.18 Priority Queue

```java
/* The elements of the priority queue are ordered according to their natural ordering*/

PriorityQueue<Integer> i = new PriorityQueue<Integer>();
PriorityQueue<Long> l = new PriorityQueue<Long>();
PriorityQueue<Double> d = new PriorityQueue<Double>();
PriorityQueue<String> s = new PriorityQueue<String>();
PriorityQueue<Character> c = new PriorityQueue<Character>(); 

Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <String> itS = s.iterator();
Iterator <Character> itC = c.iterator();

i.add(17);  or i.offer(17); 
// Inserts the specified element into this priority queue
i.poll(); 
// Retrieves and removes the head of this queue, or returns null if this queue is empty
i.peek(); 
// Retrieves, but does not remove, the head of this queue, or returns null if this queue is empty
i.remove(17);
// Removes a single instance of the specified element from this queue, if it is present
i.size(); 
// Returns the number of elements in this collection.
i.contains(17); 
// Returns true if this queue contains the specified element

while (i.size() != 0)
    System.out.println(i.poll());
```

## 14.19 Linked List

```java
LinkedList <Integer> i = new LinkedList<Integer>();
LinkedList <Long> l = new LinkedList<Long>();
LinkedList <Double> d = new LinkedList<Double>();
LinkedList <String> s = new LinkedList<String>();
LinkedList <Character> c = new LinkedList<Character>(); 

Iterator <Integer> itI = i.iterator();
Iterator <Long> itL = l.iterator();
Iterator <Double> itD = d.iterator();
Iterator <String> itS = s.iterator();
Iterator <Character> itC = c.iterator();
        
add(E e) 
// Appends the specified element to the end of this list
add(int index, E element) 
// Inserts the specified element at the specified position in this list 
addFirst(E e)
// Inserts the specified element at the beginning of this list
 addLast(E e) 
// Appends the specified element to the end of this list
clear() 
// Removes all of the elements from this list 
get(int index) 
// Returns the element at the specified position in this list 
getLast() 
// Returns the last element in this list 
indexOf(Object o) 
// Returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element
lastIndexOf(Object o) 
// Returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element

offer(E e) 
// Adds the specified element as the tail (last element) of this list
offerFirst(E e) 
//Inserts the specified element at the front of this list
offerLast(E e) 
// Inserts the specified element at the end of this list
peek() 
// Retrieves, but does not remove, the head (first element) of this list   
peekFirst() 
// Retrieves, but does not remove, the first element of this list, or returns null if this list is empty  
peekLast() 
// Retrieves, but does not remove, the last element of this list, or returns null if this list is empty 
poll() 
// Retrieves and removes the head (first element) of this list   
pollFirst() 
// Retrieves and removes the first element of this list, or returns null if this list is empty
pollLast() 
// Retrieves and removes the last element of this list, or returns null if this list is empty   
pop() 
// Pops an element from the stack represented by this list   
push(E e) 
// Pushes an element onto the stack represented by this list   
remove() 
// Retrieves and removes the head (first element) of this list   
remove(int index) 
// Removes the element at the specified position in this list   
/remove(Object o) 
// Removes the first occurrence of the specified element from this list, if it is present  
removeFirst() 
// Removes and returns the first element from this list   
removeFirstOccurrence(Object o) 
// Removes the first occurrence of the specified element in this list (when traversing the list from head to tail)
removeLast() 
// Removes and returns the last element from this list

removeLastOccurrence(Object o) 
// Removes the last occurrence of the specified element in this list (when traversing the list from head to tail) 
set(int index, E element) 
// Replaces the element at the specified position in this list with the specified element
size() 
// Returns the number of elements in this list
```

## 14.20 Data Structure Tradeoffs

TODO

## 14.21 Collections

```java
Vector<Integer> i = new Vector<Integer>(); 
i.add(10);
i.add(34);
i.add(0);
i.add(1);
i.add(100);

Comparator comparator = Collections.reverseOrder();
// Returns a comparator that imposes the reverse of the natural ordering on a collection of objects that implement the Comparable interface
Collections.sort(i, comparator); 

boolean b = Collections.disjoint(i, ii); 
// Returns true if the two specified collections have no elements in common

int f = Collections.frequency(i, 454);
// Returns the number of elements in the specified collection equal to the specified object

int res = Collections.binarySearch(i, 5); 
// binarySearch method will behave same as Arrays 

Collections.sort(i);
// Sorts the specified list into ascending order, according to the natural ordering of its elements
```

## 14.22 Calendar and Gregorian Calendar

```java
Calendar cal = Calendar.getInstance();
// get current date and time

cal.set(int year, int month, int date) 
// Sets the values for the calendar fields YEAR, MONTH, and DAY_OF_MONTH
cal.add(int field, int amount); /* cal.add(Calendar.DATE, 200) */

// adds or subtracts the specified amount of time to the given calendar field, based on the calendar's rules

int y = cal.get(Calendar.YEAR);

int m = cal.get(Calendar.MONTH);

// The first month of the year in the Gregorian and Julian calendars is JANUARY which is 0. So add one if you need

int d = cal.get(Calendar.DATE);

// The first day of the month has value 1

boolean after = born.after(when);

// true if the time of this Calendar is after the time represented by when; false otherwise

int dayOfYear = now.get(Calendar.DAY_OF_YEAR);

// Field number for get and set indicating the day number within the current year. The first day of the year has value 1

int dayOfWeek = cal.get(Calendar.DAY_OF_WEEK);
// Sunday = 1, Monday = 2

hour = cal.get(Calendar.HOUR); // 12 hour clock (0 - 11)
minute = cal.get(Calendar.MINUTE);
second = cal.get(Calendar.SECOND); 
```

## 14.23 Matcher and Pattern [ Regular Expression ]

```
Character	Matches
\d	any digit	    
\w	any word character	
\s	any whitespace	
\D	any non-digit
\W	any non-word character
\S	any non-whitespace
```

```
Quantifier	Matches
*	Matches zero or more occurrences of the pattern.
+	Matches one or more occurrences of the pattern.
?	Matches zero or one occurrences of the pattern.
{ n }	Matches exactly n occurrences.
{ n, }	Matches at least n occurrences.
{ n, m}	Matches between n and m (inclusive) occurrences.
```

## 14.24 Bit operators

The bitwise operators

| Operator | Name | Example | Result | Description |
|---|---|---|---|---|
| a & b   | and                   | 3 & 5     | 1  | 1 if both bits are 1                      |
| a \| b  | or                    | 3 \| 5    | 7  | 1 if either bit is 1                      |
| a ^ b   | xor                   | 3 ^ 5     | 6  | 1 if both bits are different Exclusive or |
| ~a      | not                   | ~3        | -4 | Inverts the bits                          |
| n << p  | left shift            | 3 << 1    | 6  |   |
| n >> p  | right shift           | 10 >> 1   | 5  |   |
| n >>> p | unsigned right shift  | 7 >>> 1   |    |   |

| A  | B  | A & B  | A \| B  | A ^ B  | ~A | ~B |
|---|---|---|---|---|---|---|
| 0  | 0  |  0 | 0  | 0 | 1 | 1 |
| 0  | 1  |  0 | 1  | 1 | 1 | 0 |
| 1  | 0  |  0 | 1  | 1 | 0 | 1 |
| 1  | 1  |  1 | 1  | 0 | 0 | 1 |

## 14.25 Base Conversion

```java
// Base Conversion  [Decimal To binary, octal and hex]

/* Integer */
String bin = Integer.toBinaryString(10);
String oct = Integer.toOctalString(10);
String hex = Integer.toHexString(10);

/* Long */
String bin = Long.toBinaryString(10);
String oct = Long.toOctalString(10);
String hex = Long.toHexString(10);

/* BigInteger */
// see BigInteger section

// Any Base to Decimal

/* Integer */

String s = sc.nextLine(); 

// int s = sc.nextInt();       /* another way */

int dec = Integer.parseInt(s,16); 
// int dec = Integer.parseInt(""+s,16); /* another way */
System.out.println(dec);
```

## 14.26 Working with \n and \r

```java
import java.util.*;
import java.io.*;

public class p458 {
    public static void main (String args[]) throws IOException  {
        
        DataInputStream dis = new DataInputStream(System.in); //input
        DataOutputStream dos = new DataOutputStream(System.out);//output
        
        while(true){
            byte b = dis.readByte(); // taking input char by char
            char c;
            if(b == 10 || b == 13)   // cheak \n and \r
                c = (char)b;
            else
                c = (char)(b-7);
            dos.writeByte(c);        // printing
        }
    }
}
```

## 14.27 Sample I/O (Nafi)

```java
/*10 10 10*/ /*20 20 20*/ /*30 30 30*/ /*10 10*/ /*20 20*/ 

import java.util.*;
public class IO {
public static void main(String [] args) {
     Scanner sc = new Scanner (System.in);
     while(true){
         int sum = 0;
         boolean linePaisi = false;
         //checking if there any line exist or not 
            while(sc.hasNextLine()){
                String line = sc.nextLine();
                if(line.equals(""))
                    break;
                linePaisi = true;
                Scanner takeInt = new Scanner(line);
                //checking if there any integer exist or not
                while(takeInt.hasNextInt()){ 
                    //sum up the integers
                    sum += takeInt.nextInt();
                }
            }
            if(linePaisi == false)
                break;
            System.out.println(sum);
        }
    }
}
```

## 14.28 Faster I/O

```java
// write flush(); at the end & and comment it before submission
/* skeleton class */ /* S.MAHBUB - UZ - ZAMAN */ /* BRACU BYTE */ 

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.io.PrintWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintStream;
import java.util.StringTokenizer; 
import java.util.Arrays;
import java.util.Hashtable;
import java.util.TreeMap;
import java.util.TreeSet;
import java.math.BigInteger;
import java.math.BigDecimal;


/* BufferedWriter */
// writer.write(); // can only print string
// writer.newLine(); // Writes a line separator

/* USE IN solve method*/
// to split on something else, use:
// st = new StringTokenizer(line, delim);
// or use this to change in the middle of parsing:
// line = st.nextToken(delim);
// for manual EOF check
// while ((line = reader.readLine()) != null)


public class A implements Runnable {
    public void solve() throws IOException {
      /* Blank line Style input
      String line;
      while(true) {
        line = reader.readLine();
        if(line.equals(""))
        break;
      }
      */

      /* TEST CASE Style input
      int T = nextInt(); 
      while(T-- > 0) {   
      }
      */

      /* EOF Style input 
      while(hasNext()) { 
      }
      */

      /* Sentinel Style input 
      while(true) { 
        int n = nextInt();
        if(n == SENTINEL)  
          break;
      }
      */
      
      // also can be written as following
      // while((n = nextInt()) != SENTINEL) 

      // writer.flush(); //comment it before submit
    }
    
    public static void main(String args []) {
        new A().run();   
    }
    
    BufferedReader reader;     
    StringTokenizer tokenizer;
    // BufferedWriter writer;
    PrintWriter writer;
    
    public void run() {
        
        try {         
            reader = new BufferedReader(new InputStreamReader(System.in)); /* console input */
            // reader = new BufferedReader (new FileReader ("input path")); /* file input */
            tokenizer = null;
            // writer = new BufferedWriter(new OutputStreamWriter(System.out)); /* console output */
            // writer = new BufferedWriter (new FileWriter ("output path")); /* file output */
            // writer = new PrintWriter (new FileWriter ("output path")); /* file output */
            writer = new PrintWriter(System.out); /* console output */
            solve();             
            reader.close();
            writer.close();
        } catch (Exception e) {
            e.printStackTrace(); // for debugging
            // System.exit(1);
        }
    }
    
    
    boolean hasNext() throws IOException {
        
        while (tokenizer == null || !tokenizer.hasMoreTokens()) {   
            
            String s = reader.readLine();
            
            if (s == null) 
                return false;
            
            tokenizer = new StringTokenizer(s);
            
        }
        return true;
    }
    
    String next() throws IOException {      
        hasNext();
        return tokenizer.nextToken();
    }
    
    String nextLine() throws IOException {   
        hasNext();
        return tokenizer.nextToken("\n\r");
    }
    
    int nextInt() throws IOException {
        hasNext();
        return Integer.parseInt(tokenizer.nextToken()); 
    }

    long nextLong() throws IOException {
        hasNext();
        return Long.parseLong(tokenizer.nextToken()); 
    }
    
    double nextDouble() throws IOException {
        hasNext();
        return Double.parseDouble(tokenizer.nextToken()); 
    }
    
    BigInteger nextBigInteger() throws IOException { 
        hasNext();
        return new BigInteger(tokenizer.nextToken()); 
    }
    
    BigDecimal nextBigDecimal() throws IOException {
        hasNext();
        return new BigDecimal(tokenizer.nextToken()); 
    } 
}
```

## 14.29 printf

| Code | Description                        |
|------|------------------------------------|
| %c   | character                          |
| %d   | decimal (integer) number (base 10) |
| %e   | exponential floating-point number  |
| %f   | floating-point number              |
| %i   | integer (base 10)                  |
| %o   | octal number (base 8)              |
| %s   | a string of characters             |
| %u   | unsigned decimal (integer) number  |
| %x/%X | in hexadecimal (base 16) [for x digits 0-9 and letters a-f and for X digits 0-9 and letters A-F] |
| e/E | Display a floating-point value in exponential notation [1.000000e+02/1.000000E+02] |
| a/A | Display a floating-point value in hexadecimal format |
| g/G | 10^-5 < floating-point value is printed in format %f < and 10^-6 => value < floating-point value is printed in format %e/%E >= 10^6 |
| %% | print a percent sign |
| \% | print a percent sign |

### Controlling printf integer width
The "%3d" specifier means a minimum width of three spaces, which, by default, will be right-justified. (Note: the alignment is not currently being displayed properly here.)

| Code                       | Description |
|----------------------------|-------------|
| printf("%3d", 0);          | 0           |
| printf("%3d", 123456789);  | 123456789   |
| printf("%3d", -10);        | -10         |
| printf("%3d", -123456789); | -123456789  |

### Left-justifying printf integer output
To left-justify those previous printf examples, just add a minus sign (-) after the % symbol, like this:

| Code                        | Description |
|-----------------------------|-------------|
| printf("%-3d", 0);          | 0           |
| printf("%-3d", 123456789);  | 123456789   |
| printf("%-3d", -10);        | -10         |
| printf("%-3d", -123456789); | -123456789  |

### The printf zero-fill option
To zero-fill your printf integer output, just add a zero (0) after the % symbol, like this:

| Code                        | Description |
|-----------------------------|-------------|
| printf("%03d", 0);          | 0           |
| printf("%03d", 1);          | 1           |
| printf("%03d", 123456789);  | 123456789   |
| printf("%03d", -10);        | -10         |
| printf("%03d", -123456789); | -123456789  |


### printf integer formatting
Here is a collection of printf examples for integer printing. Several different options are shown, including a minimum width specification, left-justified, zero-filled, and also a plus sign for positive numbers.

| Description                          | Code                   | Result    |
|--------------------------------------|------------------------|-----------|
| At least five wide                   | printf("'%5d'", 10);   | `' 10'`   |
| At least five-wide, left-justified   | printf("'%-5d'", 10);  | `'10 '`   |
| At least five-wide, zero-filled      | printf("'%05d'", 10);  | `'00010'` |
| At least five-wide, with a plus sign | printf("'%+5d'", 10);  | `' +10'`  |
| Five-wide, plus sign, left-justified | printf("'%-+5d'", 10); | `'+10 '`  |

Here are several examples showing how to print floating-point numbers with printf.

| Description                                                 | Code                                | Result           |
|-------------------------------------------------------------|-------------------------------------|------------------|
| Print one position after the decimal                        | printf("'%.1f'", 10.3456);          | `'10.3'`         |
| Two positions after the decimal                             | printf("'%.2f'", 10.3456);          | `'10.35'`        |
| Eight-wide, two positions after the decimal                 | printf("'%8.2f'", 10.3456);         | `' 10.35'`       |
| Eight-wide, four positions after the decimal                | printf("'%8.4f'", 10.3456);         | `' 10.3456'`     |
| Eight-wide, two positions after the decimal, zero-filled    | printf("'%08.2f'", 10.3456);        | `'00010.35'`     |
| Eight-wide, two positions after the decimal, left-justified | printf("'%-8.2f'", 10.3456);        | `'10.35 '`       |
| Printing a much larger number with that same format         | printf("'%-8.2f'", 101234567.3456); | `'101234567.35'` |

### printf string formatting
Here are several printf formatting examples that show how to format string output with printf format specifiers.


| Description                    | Code                        | Result     |
|--------------------------------|-----------------------------|------------|
| A simple string                | printf("'%s'", "Hello");    | `'Hello'`  |
| A string with a minimum length | printf("'%10s'", "Hello");  | `' Hello'` |
| Minimum length, left-justified | printf("'%-10s'", "Hello"); | `'Hello '` |

Here are a few examples of how to use these special characters:

| Description                        | Code                    | Result      |
|------------------------------------|-------------------------|-------------|
| Insert a tab character in a string | printf("Hello\tworld"); | Hello world |
| Insert a newline character in a string |	printf("Hello\nworld"); | "Hello<br>world" |
| Typical use of the newline character|	printf("Hello world\n"); |	Hello world |
| A DOS/Windows path with backslash characters | printf("C:\\Windows\\System32\\");	| C:\Windows\System32\ |

Summary of special printf characters

| Code | Description          |
|------|----------------------|
| \a   | audible alert        |
| \b   | backspace            |
| \f   | form feed            |
| \n   | newline, or linefeed |
| \r   | carriage return      |
| \t   | horizontal tab       |
| \v   | vertical tab         |
| \\   | backslash            |
| \’   | single quote         |
| \”   | double quote         |

### Flags [There are seven flags]

| Code          | Description                                                                                                                                                       |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -(minus sign) | Left justify the output within the specified filed [printf("%-10d\n",a);]                                 |
| #ERROR!       | display a plus sign preceding positive values and a minus sign preceding negative values                  |
| space         | print a space before a positive value not printed with the + falg                                         |
| #             | prefix 0 to the output value when used with the octal conversion character o. Prefix 0x to the output value when used with the hexadecimal conversion character x |
| 0(zero)       | Pad a filed with leading zeros                                                                                                                                    |
| ,(comma)      | Use the local-specific thousands separator (for U.S. local) to display decimal and floating point numbers                                                         |
| (             | Enclose negative numbers in parentheses |

```java
Calendar dateTime = Calendar.getInstance();

System.out.printf( "%tc\n", dateTime );
System.out.printf( "%tF\n", dateTime );
System.out.printf( "%tD\n", dateTime );
System.out.printf( "%tr\n", dateTime );
System.out.printf( "%tT\n", dateTime );

// printing with conversion characters for date
System.out.printf( "%1$tA, %1$tB %1$td, %1$tY\n", dateTime );
System.out.printf( "%1$TA, %1$TB %1$Td, %1$TY\n", dateTime );
System.out.printf( "%1$ta, %1$tb %1$te, %1$ty\n", dateTime );

// printing with conversion characters for time
System.out.printf( "%1$tH:%1$tM:%1$tS\n", dateTime );
System.out.printf( "%1$tZ %1$tI:%1$tM:%1$tS %tP", dateTime );
```

```
Tue Jun 29 11:17:21 GMT-05:00 2004
2004-06-29
06/29/04
11:17:21 AM
11:17:21
Tuesday, June 29, 2004
TUESDAY, JUNE 29, 2004
Tue, Jun 29, 04
11:17:21
GMT-05:00 11:17:21 AM
```

### Reordering output with argument indices

```
String s1 = "I";
String s2 = "Love";
String s3 = "ACM";
System.out.printf("%s %s %s\n", s1, s2, s3);
System.out.printf("%3$s %2$s %1$s\n", s1, s2, s3);
// Output:
// I Love ACM
// ACM Love I
```

## 14.30 Mathematical Library Functions 

| In Mathematics      | In Java                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------|
| Square root of x    | Math.sqrt(x)                                                                                                         |
| Cube root of x      | Math.cbrt(x)                                                                                                         |
| Absolute value of x | Math.abs(x)                                                                                                          |
| xy                  | Math.pow(x, y) or <br>Math.exp(Math.log10(x) * y)                                                                    |
| ex                  | Math.exp(x)                                                                                                          |
| loge(x)             | Math.log(x)                                                                                                          |
| log10(x)            | Math.log10(x)                                                                                                        |
| Floor               | Math.floor(x) <br> Round down to nearest integer                                                                     |
| Ceil                | Math. ceil (x) <br>Round up to nearest integer                                                                       |
| Value of PI         | Math.PI (3.141592653589793d)                                                                                         |
| Value of E          | Math.E (2.718281828459045d)                                                                                          |
| Random              | Math.random() <br> Returns randomly a number greater than or equal to 0.0 and less than 1.0                          |
| Max                 | Math.max(x a , y b)<br>x = double, float, long, int<br>y = double, float, long, int<br>Return maximum of two numbers |
| Min                 | Math.min(x a , y b)<br>x = double, float, long, int<br>y = double, float, long, int<br>Return minimum of two numbers |
| Exp                 | Math.exp(double a)<br>Returns Euler's number e raised to the power of a double value                                 |
| toRadians           | Math.toRadians(d) <br>Returns d (angle in degrees) converted to radians                                              |
| toDegrees           | Math.toDegrees(ar) <br>Returns ar (angle in radians) converted to degrees                                            |
| asin                | Math.asin(double a) Returns sine inverse value in radians                                                            |
| acos                | Math.acos(double a)<br>Returns cosine inverse value in radians                                                       |
| atan                | Math.atan(double a) <br>Returns tangent inverse value in radians                                                     |
| atan                | Math.atan(double a)   Returns tangent inverse value in radians                                                       |
| atan2               | Math.atan2(double y, double x) Converts Cartesian coordinates to polar coordinates                                   |
| IEEEremainder       | Math. IEEEremainder(double f1, double f2) Returns the closest difference between the remainder and the divisor       |
| Sinx                | Math.sin(x) <br>Return in radian                                                                                     |
| Cosx                | Math.cos(x)<br>Return in radian                                                                                      |
| Tanx                | Math.tan(x) <br>Return in radian                                                                                     |
| sinx                | Math.sin(x*Math.PI/180) <br>Return in degree                                                                         |

```java
public class MathLibraryExample {

  public static void main(String[] args) {
    
    int i = 7;
    int j = -9;
    double x = 72.3;
    double y = 0.34;
  

    // Truncating and Rounding functions
 
    // You can round off a floating point number  
    // to the nearest integer with round()
     System.out.println(x + " is approximately " + Math.round(x));     
     System.out.println(y + " is approximately " + Math.round(y));     

    // The "ceiling" of a number is the   
    // smallest integer greater than or equal to
    // the number. Every integer is its own 
    // ceiling.
     System.out.println("The ceiling of " + i + " is " + Math.ceil(i));     
     System.out.println("The ceiling of " + j + " is " + Math.ceil(j));
     System.out.println("The ceiling of " + x + " is " + Math.ceil(x));     
     System.out.println("The ceiling of " + y + " is " + Math.ceil(y));

     // The "floor" of a number is the largest  
     // integer less than or equal to the number.
     // Every integer is its own floor.
     System.out.println("The floor of " + i + " is " + Math.floor(i));     
     System.out.println("The floor of " + j + " is " + Math.floor(j));
     System.out.println("The floor of " + x + " is " + Math.floor(x));     
     System.out.println("The floor of " + y + " is " + Math.floor(y));

     // Comparison operators

     System.out.println("Pi is " + Math.PI);     
     System.out.println("e is " + Math.E);       
     // Trigonometric methods
    // All arguments are given in radians
 
    // Convert a 45 degree angle to radians
    double angle = 45.0 * 2.0 * Math.PI/360.0;
    System.out.println("cos(" + angle + ") is " + Math.cos(angle));     
    System.out.println("sin(" + angle + ") is " + Math.sin(angle));     

    // Exponential and Logarithmic Methods
  
    // exp(a) returns e (2.71828...) raised 
    // to the power of a.   
    System.out.println("exp(1.0) is "  + Math.exp(1.0));

    // log(a) returns  the natural logarithm (base e) of a. 
    System.out.println("log(1.0) is "    + Math.log(1.0));
   }
}
```

```
Here's the output from the math library example 
1.	72.3 is approximately 72
2.	0.34 is approximately 0
3.	The ceiling of 7 is 7
4.	The ceiling of -9 is -9
5.	The ceiling of 72.3 is 73
6.	The ceiling of 0.34 is 1
7.	The floor of 7 is 7
8.	The floor of -9 is -9
9.	The floor of 72.3 is 72
10.	The floor of 0.34 is 0
11.	e is 2.71828
12.	exp(1.0) is 2.71828
13.	log(1.0) is 0
```

| Double Number | Floor | rint | ceil | round |
|---------------|-------|------|------|-------|
| 0             | 0     | 0    | 0    | 0     |
| 0.1           | 0     | 0    | 1    | 0     |
| 0.2           | 0     | 0    | 1    | 0     |
| 0.3           | 0     | 0    | 1    | 0     |
| 0.4           | 0     | 0    | 1    | 0     |
| 0.5           | 0     | 0    | 1    | 1     |
| 0.6           | 0     | 1    | 1    | 1     |
| 0.7           | 0     | 1    | 1    | 1     |
| 0.8           | 0     | 1    | 1    | 1     |
| 0.9           | 0     | 1    | 1    | 1     |
| 1             | 0     | 1    | 1    | 1     |
| 1.1           | 1     | 1    | 2    | 1     |
| 1.2           | 1     | 1    | 2    | 1     |
| 1.3           | 1     | 1    | 2    | 1     |
| 1.4           | 1     | 1    | 2    | 1     |
| 1.5           | 1     | 2    | 2    | 2     |
| 1.6           | 1     | 2    | 2    | 2     |
| 1.7           | 1     | 2    | 2    | 2     |
| 1.8           | 1     | 2    | 2    | 2     |
| 1.9           | 1     | 2    | 2    | 2     |
| 2             | 2     | 2    | 3    | 2     |
| 2.1           | 2     | 2    | 3    | 2     |


Our explanation: 

floor: largest integer that is smaller than given number

ceil: smallest integer that is larger than given number

rint: round given number (convert to int) to closer int

round: (int)(given number + 0.5)

Java doc’s explanation:

static double ceil(double a) 
          Returns the smallest (closest to negative infinity) double value that is not less than the argument and is equal to a mathematical integer.

static double floor(double a) 
          Returns the largest (closest to positive infinity) double value that is not greater than the argument and is equal to a mathematical integer.

static double rint(double a) 
          Returns the double value that is closest in value to the argument and is equal to a mathematical integer. 

static long round(double a) 
          Returns the closest long to the argument.


## 14.31 Java Primitive Data Types

| Type    | Contains                | Default | Size    | Range                                                                      |
|---------|-------------------------|---------|---------|----------------------------------------------------------------------------|
| boolean | true or false           | FALSE   | 1 bit   | NA                                                                         |
| char    | Unicode character       | \u0000  | 16 bits | \u0000 to \uFFFF                                                           |
| byte    | Signed integer          | 0       | 8  bits | -128 to 127 [ -2^7 to 2^7-1 ]                                              |
| short   | Signed integer          | 0       | 16 bits | -32,768 to 32,767 [ -2^15 to 2^15-1]                                       |
| int     | Signed integer          | 0       | 32 bits | -2,147,483,648 to 2,147,483,647 [ -2^31 to 2^31-1 ]                        |
| long    | Signed integer          | 0       | 64 bits | -9,223,372,036,854,775,808  to 9,223,372,036,854,775,807 [-2^63 to 2^63-1] |
| float   | IEEE 754 floating point | 0       | 32 bits | ±1.4E-45 to ±3.4028235E+38                                                 |
| double  | IEEE 754 floating point | 0       | 64 bits | ±4.9E-324 to ±1.7976931348623157E+308                                      |

## 14.32 Others

```java
/* Conversion [int, double, long, float to String] */
int to String:
String myString = Integer.toString(i)
double to String: 
String str = Double.toString(d);
long to String: 
String str = Long.toString(l);
float to String: 
String str = Float.toString(f);
```

```java
/* Conversion [String to int, double, long, float] */
String to int: 
int i = Integer.parseInt(str);
String to double: 
double d = Double.parseDouble(s);
String to long: 
long l = Long.parseLong(str);
String to float: 
float d = Float.parseFloat(s);
```

```java
/* integer to boolean */
int i; // 1 or 0
boolean b = (i != 0);
```

```java
/* boolean to integer */
boolean b; // true or false
int i = (b) ? 1 : 0;
```

```java
/* char to ASCII code */
char c = 'A';
int i = (int) c;
```

```java
/* ASCII code to char */
char c = 'A';
int i = (int) c;
```

```java
/* This Will Eat the Enter */
int x = Integer.parseInt(sc.nextLine());
long x = Long.parseLong(sc.nextLine());
double x = Double.valueof(sc.nextLine());
float x = Float.valueof(sc.nextLine());
```

```
// from cmd

Compilation:  javac className.java
Execution:    java className 
```

```
// batch file

java className <input.txt>output.txt

1. Save as .cmd or .bat
2. Win7 (run as administrator)
```

```java
/* ternary operator */
if operand1 is true, operand2 is returned, else operand3 is returned 
      operand1 ? operand2 : operand3

      true ? op2 : op3                // operand2 returned
      false ? op2 : op3               // operand3 returned

a = (n % 2 == 0) ? 100 : 200;

The above expression is equivalent to
if(n % 2 == 0) 
   a = 100;
else
   a = 200;
```

```java
/* Multiple loop breaks */
anyname: // usally used outerloop:
for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
         if (i * j > 6) {
             System.out.println("Breaking");
             break anyname;
         }
     }
}
```

```java
/* do while loop */
int i  = 1;
do {
    System.out.println(i++);
} while (i < 5);

// no matter what goes wrong, this loop at least execute once
```

```java
Integer.MAX_VALUE 
/* A constant holding the maximum value an int can have, 231-1 */
Integer.MIN_VALUE 

/* A constant holding the minimum value an int can have, -231 */
```

```java
Long.MAX_VALUE

/* A constant holding the maximum value a long can have, 263-1 */

Long.MIN_VALUE

/* A constant holding the minimum value a long can have, -263 */
```

```java
Double.POSITIVE_INFINITY

/* A constant holding the positive infinity of type double. It is equal to the value returned by Double.longBitsToDouble(0x7ff0000000000000L) */
Double. NEGATIVE_INFINITY 

/* A constant holding the negative infinity of type double. It is equal to the value returned by Double.longBitsToDouble(0xfff0000000000000L) */
```

```java
Double.MAX_VALUE
/* A constant holding the largest positive finite value of type double, (2-2-52)·21023. It is equal to the hexadecimal floating-point literal 0x1.fffffffffffffP+1023 and also equal to Double.longBitsToDouble(0x7fefffffffffffffL) */
Double.MIN_VALUE 

/* A constant holding the smallest positive nonzero value of type double, 2-1074. It is equal to the hexadecimal floating-point literal 0x0.0000000000001P-1022 and also equal to Double.longBitsToDouble(0x1L) */
```

```java
for (type var : arr){
    body-of-loop
}

for (int i = 0; i < arr.length; i++){ 
    type var = arr[i];
    body-of-loop
}

for (type var : coll){
    body-of-loop
}

for (Iterator<type> iter = coll.iterator(); iter.hasNext();){
    type var = iter.next();
    body-of-loop
}
```
