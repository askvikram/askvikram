---
id: 155
title: 'Java String to Int &#8211; Definitive Guide'
date: '2021-03-16T16:53:59+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.stackvidhya.com/?p=155'
permalink: /java-string-to-int/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_seo_score:
    - '80'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_primary_category:
    - '2'
inline_featured_image:
    - '0'
rank_math_focus_keyword:
    - 'java string to int'
rank_math_description:
    - 'In this tutorial, you''ll convert java string to int using parseInt() method, convert without parseInt(), convert string to int without exception and convert string to int with leading zeros. '
rank_math_analytic_object_id:
    - '52'
ss_social_share_disable:
    - '0'
socialsnap_share_count_timestamp:
    - '2023-09-15 20:04:22'
ss_total_share_count:
    - '0'
categories:
    - java
tags:
    - conversion
    - java
    - 'string to int'
---

To convert Java `String` to `Int` is one of the commonly used operation in the Java programs. There are 8 methods available to perform this conversion.

**You can convert Java `String` to `Int` using `Integer.parseInt()` method or `Integer.valueOf()` method.**

In this tutorial, you’ll learn

- Java APIs available to convert `String` to `int` or `Integer`
- External Libraries available to convert `String` to `Int`
- When to use the different methods
- Exceptions to be handled

The recommended method to convert `String` to `int` is using the Java API itself as given below.

```
<pre class="wp-block-code">```
try {
    final int result = Integer.parseInt(numAsString);

    System.out.println("String converted to number using Integer.parseInt : " + result);

    } catch (final NumberFormatException e) {

        System.err.println("Unable to convert String  " + numAsString
                    + " to int. A NumberFormatException Occured, Ensure the string contains only valid numbers " + e);
    }
```
```

Read the below detailed methods to understand how to convert Java `String` to `int` using various methods available and when its appropriate to use each method.

## <span class="ez-toc-section" id="using_integerparseint"></span>Using Integer.parseInt()<span class="ez-toc-section-end"></span>

You can easily convert `String` to `Int` in java using the `Integer.parseInt()` method available by default in Java.

There are two overloaded methods available in `Integer.parseInt()` as explained below

### <span class="ez-toc-section" id="integerparseintstring_str"></span>Integer.parseInt(String Str)<span class="ez-toc-section-end"></span>

[Integer.ParseInt(String str)](https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#parseInt%28java.lang.String%29) accepts only a `String` which needs to be converted to int.

**When to Use**

Use this method when you want to convert a String which has only numbers and a default [radix](https://en.wikipedia.org/wiki/Radix) shall be used to convert.

**Points to Note**

The **leading zeros will be ignored** when converting `String` to `int` using the `parseInt()` method.

If you want **to preserve the leading zeros, then do not use this method.**

**Snippet**

The below is the code snippet to convert the `string` to `int`.

```
<pre class="wp-block-code">```
final int result = Integer.parseInt(numAsString);
```
```

**Returns**

A primitive `int` type representing the `String`.

**Exceptions to Handle**

The `Integer.parseInt()` throws the `NumberFormatException` in the following cases.

- If the `String` is `null` or Empty.
- If the `String` is not a parse-able integer. For e.g., it contains any characters other than numbers. **Except the – sign** which can be used to denote a negative number.

### <span class="ez-toc-section" id="using_integerparseintstring_to_convert_with_leading_zeros"></span>Using Integer.parseInt(String) to Convert With Leading Zeros<span class="ez-toc-section-end"></span>

If you want to convert `String` to `int` **with leading zeros**, then use the below code snippet.

**%05d** in the string format method specifies, 5 digit leading zeros should be preserved.

```
<pre class="wp-block-code">```
public static void main(String args[]){

      String str="0000077";
      
      str = String.format("%05d", Integer.parseInt(str));

      System.out.println("Output String: "+str);

  }
```
```

### <span class="ez-toc-section" id="integerparseintstring_str_int_radix"></span>Integer.parseInt(String Str, Int Radix)<span class="ez-toc-section-end"></span>

[Integer.parseInt(String str, int radix)](%28https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#parseInt%28String,%20int) accepts a `String` to be converted to `int` and a `radix` to convert the `String` to a specific radix.

**When to Use**

You can use this method if you want to convert a `String` to `int` with specified Radix.

**Code snippet**

The below code is used to convert the `String` to int in the specified Radix.

```
<pre class="wp-block-code">```
final int result = Integer.parseInt(numAsString,10);
```
```

**Returns**

A primitive `int` type representing the `String`.

**Exceptions to Handle**

The `Integer.parseInt()` throws the `NumberFormatException` in the following cases.

- If the `String` is `null` or Empty.
- If the `String` is not a parse-able integer. For e.g., it contains any characters other than numbers. **Except the – sign** which can be used to denote a negative number.

**Example Program**

Below example shows how to use the `Integer.parseInt() `with `NumberFormatException. `

```
<pre class="wp-block-code">```
private static void convertUsingParseInt() {

        final String numAsString = "-500";

        try {

            final int result = Integer.parseInt(numAsString);

            System.out.println("String converted to number using Integer.parseInt : " + result);

        } catch (final NumberFormatException e) {

            System.err.println("Unable to convert String  " + numAsString
                    + " to int. A NumberFormatException Occured, Ensure the string contains only valid numbers " + e);

        }
    }
```
```

## <span class="ez-toc-section" id="using_integervalueof"></span>Using Integer.valueOf()<span class="ez-toc-section-end"></span>

You can easily convert `String` to Integer in Java using the `Integer.valueof()` method. This can be used to convert Java `string` to `Integer `without `parseInt()` method.

There are two overloaded methods available as explained below.

### <span class="ez-toc-section" id="using_integervalueofstring_s"></span>Using Integer.valueOf(String S)<span class="ez-toc-section-end"></span>

[Integer.valueOf(String s)](https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#valueOf%28java.lang.String%29) accepts only a `String` object to be converted to Integer.

**When to Use**

You can use this method, if you want to convert `String` to an `Integer` Object rather than the primitive int.

**Returns**

Returns `Integer` object representing the `String`.

If the `Integer` object is already available in the cache, then it returns the cached object.

Else it returns the **new `Integer` object**.

**Code snippet**

Below Snippet is used to convert to the `String` to `Integer` using `valueOf()`.

```
<pre class="wp-block-code">```
final int result = Integer.valueOf(numAsString);
```
```

**Exceptions to Handle**

[NumberFormatException](https://docs.oracle.com/javase/7/docs/api/java/lang/NumberFormatException.html) will be thrown by `Integer.valueOf(String s)` in following scenarios.

- If the `String` is null or empty
- If the `String` contains any characters other than integers. **Except the ‘-‘ sign** which can be used to denote the negative number.

**Example Program**

The below example shows how to convert `String` to `Integer` using the `valueOf()` method.

```
<pre class="wp-block-code">```
/**
     * 
     */
    private static void convertUsingValueOf() {

        final String numAsString = "500";

        try {

            final int result = Integer.valueOf(numAsString);

            System.out.println("String converted to number using Integer.valueOf : " + result);

        } catch (final NumberFormatException e) {

            System.err.println("Unable to convert String  " + numAsString
                    + " to int. A NumberFormatException Occured, Ensure the string contains only valid numbers " + e);

        }
    }
```
```

## <span class="ez-toc-section" id="using_apache_commons_lang3"></span>Using Apache Commons Lang3<span class="ez-toc-section-end"></span>

[Apache Commons Lang](https://commons.apache.org/proper/commons-lang/) is a provides lot of helper methods for Java.lang API, especially `String` manipulations, `Number` conversions, objects reflections etc.

Latest Commons Lang3 Version: [3.11](https://commons.apache.org/proper/commons-lang/javadocs/api-release/index.html)

You can download the binaries of the Commons Lang from this [link](https://mirrors.estointernet.in/apache//commons/lang/binaries/commons-lang3-3.12.0-bin.zip).

[Here](https://commons.apache.org/proper/commons-lang/download_lang.cgi) is the download home page to get the other format of the binaries.

**Pom File**

To add commons lang as a dependency in Maven project, add the below code to your POM file.

```
<pre class="wp-block-code">```
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.12.0</version>
</dependency>
```
```

**Gradle Location**

```
<pre class="wp-block-code">```
implementation group: 'org.apache.commons', name: 'commons-lang3', version: '3.12.0'
```
```

You can use the `toInt()` available in the [`NumberUtils`](https://commons.apache.org/proper/commons-lang/apidocs/org/apache/commons/lang3/math/NumberUtils.html#toInt-java.lang.String-int-) class of Commons lang API.

Now, you’ll see how to use the two different `NumberUtils.toInt()` to perform the convert operation.

### <span class="ez-toc-section" id="numberutilstointstring_str"></span>NumberUtils.toInt(String Str)<span class="ez-toc-section-end"></span>

[NumberUtils.toInt(String str)](https://commons.apache.org/proper/commons-lang/apidocs/org/apache/commons/lang3/math/NumberUtils.html#toInt-java.lang.String-) accepts only the `String` object that will be converted to `int`.

This can be used to convert Java `string` to `int `without `exception` and it is `null` safe.

**When to Use**

Use if you do not want to handle any `exception` explicitly.

**Returns**

`int` represented by the `String` object.

`<strong>0</strong>` – if the conversion fails due to any error or exception.

**Code snippet**

Use the below snippet to convert to `String` to `int` using toInt().

```
<pre class="wp-block-code">```
final int result = NumberUtils.toInt(numAsString);
```
```

**Exceptions to Handle**

No exceptions to Handle as **it returns 0 in case of exceptions**.

**Example Program**

The below example shows how to convert `String` to `Integer` using the `toInt()` method.

```
<pre class="wp-block-code">```
/**
     * 
     */
    private static void convertUsingValueOf() {

        final String numAsString = "500";

        final int result = NumberUtils.toInt(numAsString);

        System.out.println("String converted to number using NumberUtils.toInt() : " + result);

    }
```
```

### <span class="ez-toc-section" id="using_numberutilstointstring_str_int_defaultvalue"></span>Using NumberUtils.toInt(String Str, Int defaultValue)<span class="ez-toc-section-end"></span>

[NumberUtils.toInt(String str, int defaultValue)](https://commons.apache.org/proper/commons-lang/apidocs/org/apache/commons/lang3/math/NumberUtils.html#toInt-java.lang.String-int-) accepts the `String` object that will be converted to `int` and a default value which should be returned in case if the conversion fails.

This can be used to convert Java `string` to `int` without `exception` and it is `null` safe.

**When to Use**

Use if you want to use any default value in case of failed conversion.

**Returns**

`int` represented by the string object, if the conversion is successful.

Default value, if the conversion fails due to any `Exception`.

**Code snippet**

Use the below snippet to convert to the `String` to `int` using `toInt()`.

```
<pre class="wp-block-code">```
final int result = NumberUtils.toInt(numAsString,1);
```
```

**Exceptions to Handle**

No exceptions to Handle as it returns the `defaultValue` in case of exceptions.

**Example Program**

The below example shows how to convert `String` to `int` using the `toInt()` method.

```
<pre class="wp-block-code">```
/**
     * 
     */
    private static void convertUsingtoInt() {

        final String numAsString = "500";

        final int result = NumberUtils.toInt(numAsString, 1);

        System.out.println("String converted to number using NumberUtils.toInt() : " + result);

    }
```
```

## <span class="ez-toc-section" id="using_isdigit_and_parseint"></span>Using isDigit() and parseInt()<span class="ez-toc-section-end"></span>

In this section, you’ll use the user defined function `isDigit()` to check if the given String is a proper number which can be converted to int or if it contains any characters which cannot be converted to `int` or `Integer` object.

This can also be used to convert Java `string` to `int` without `exception`.

If its a proper digit, then you can use `parseInt()` method available in the `Integer` class to convert `String` to `Int` primitive type and it is `null` safe.

**When to Use**

Use if

- You want to **check if the string is a proper number** before converting.
- You **do not want** to handle `NumberFormatException` in your program.

**Example Program**

In the below example class name `StringtoIntExamples`, `isDigit()` method is used to check if its a convertible `String` and then convert to `int`.

```
<pre class="wp-block-code">```
public class StringtoIntExamples {

    public static void main(final String[] args) {

        convertUsingParseInt();

    }

    /**
     * @param input
     * @return
     */
    public static boolean isDigit(final String inputString) {

        // input is null or an Empty String, return false.

        if (inputString == null || inputString.isEmpty())

            return false;

        if (inputString.startsWith("-"))

            // negative number in string, cut the first char
             return inputString.substring(1).matches("[0-9]*");

        else

            // positive number return true for converting to int
            return inputString.matches("[0-9]*");


    }

    /**
     * Method to convert Java String to int using Integer parseInt.
     */
    private static void convertUsingParseInt() {

        String number = "-100"; 

        if (isDigit(number)) {      

            System.out.println(Integer.parseInt(number));
 
        } 
        else {
 
            System.out.println("Please provide a String containing only numbers");
 
        }
    }
```
```

## <span class="ez-toc-section" id="using_java_8_optional_and_streams"></span>Using Java 8 Optional and Streams<span class="ez-toc-section-end"></span>

In this section, you’ll learn how to use Java8 `Optional()` and `Streams` to convert `String` to `int`.

[Optional](https://docs.oracle.com/javase/8/docs/api/java/util/Optional.html) is a container object in java which may or may not contain values. This can be used when you want to avoid null check of any objects.

[Streams](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html) are Classes which supports functional-style operations on streams of elements, such as map-reduce transformations on collections.

This is `null` safe method.

**Snippet**

```
<pre class="wp-block-code">```
final Optional<Integer> result = Optional.ofNullable(number).filter(StringtoIntExamples::isDigit)
                .map(Integer::parseInt);
```
```

where

- **Optional.ofNullable(number)** – Checks if the `String` is `null` or not
- **filter(StringtoIntExamples::isDigit)** – Checks if the `String` is a proper digit. Uses the `isDigit()` user defined method available in the `StringtoIntExamples` class.
- **map(Integer::parseInt)** – Converts the `String` to `int` using the `Integer.parseInt()` using `Streams`.

**Example**

If the String is not null, and a proper number means, then the resultant `Optional` object will return `true` when checked with `isPresent()`.

`If` true then, return the number. `Else` display appropriate message to user.

```
<pre class="wp-block-code">```
/**
     * Method to convert Java String to int using Java 8 optional.
     */
    private static void convertUsingOptional() {

        final String number = "10";

        final Optional<Integer> result = Optional.ofNullable(number).filter(StringtoIntExamples::isDigit)
                .map(Integer::parseInt);

        if (result.isPresent())
            System.out.println(result.get());
        else
            System.out.println("Please provide a valid digit [0-9]");

    }
```
```

This is how you can use Java8 `Optional` and `Stream` to convert `String` to `Integer`.

## <span class="ez-toc-section" id="using_google%e2%80%99s_guava_library"></span>Using Google’s Guava Library<span class="ez-toc-section-end"></span>

Google has a java core library called Guava with multiple utility methods and additional collection types.

You can use the `tryParse()` method available [Ints](https://guava.dev/releases/19.0/api/docs/com/google/common/primitives/Ints.html) class of Guava library to convert `String` to `int` without `exception` in case of problems.

Latest Google Guava Version: [30.1.1](https://github.com/google/guava/releases)

You can download the binaries of the Google Guava from this [link](http://search.maven.org/remotecontent?filepath=com/google/guava/guava/23.0/guava-23.0.jar).

[Here](https://commons.apache.org/proper/commons-lang/download_lang.cgi) is the download home page to get the other format of the binaries.

**Pom File**

To add commons lang as a dependency in Maven project, add the below code to your POM file.

```
<pre class="wp-block-code">```
<dependency>
  <groupId>com.google.guava</groupId>
  <artifactId>guava</artifactId>
  <version>30.1.1-jre</version>
  <!-- or, for Android: -->
  <version>30.1.1-android</version>
</dependency>
```
```

**Gradle Location**

```
<pre class="wp-block-code">```
dependencies {
  // Pick one:

  // 1. Use Guava in your implementation only:
  implementation("com.google.guava:guava:30.1.1-jre")

  // 2. Use Guava types in your public API:
  api("com.google.guava:guava:30.1.1-jre")

  // 3. Android - Use Guava in your implementation only:
  implementation("com.google.guava:guava:30.1.1-android")

  // 4. Android - Use Guava types in your public API:
  api("com.google.guava:guava:30.1.1-android")
}
```
```

### <span class="ez-toc-section" id="using_tryparsestring_str"></span>Using tryParse(String Str)<span class="ez-toc-section-end"></span>

[tryParse(String str)](https://guava.dev/releases/19.0/api/docs/com/google/common/primitives/Ints.html#tryParse%28java.lang.String%29) parses the string into a signed decimal `Integer` value. This method accepts only ascii digits and the `+` ascii sign is **rejected by default**.

**When to Use**

You can use this method, **if you want to avoid validation** if the string is a valid number.

It is also `null` safe.

**Returns**

- Number representing the String

**Code snippet**

```
<pre class="wp-block-code">```
Integer result = Ints.tryParse(givenString);
```
```

**Exceptions to Handle**

No exception needs to be handled explicitly. It returns `null` if there is a problem during conversion.

**Example Program**

```
<pre class="wp-block-code">```
/**
* 
*/
private int void convertUsingtoInt(String numAsString) {

    final int result = Ints.tryParse(numAsString);

    System.out.println("String converted to number using NumberUtils.toInt() : " + result);

    return result;
}
```
```

## <span class="ez-toc-section" id="using_integerdecode"></span>Using Integer.decode()<span class="ez-toc-section-end"></span>

[Integer.decode()](https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#decode%28java.lang.String%29) works similar to Integer.valueOf() but accepts different representations such as decimal, hexadecimal and octal numbers.

**When to Use**

Use when you want to convert a `String` with `decimal`, `hexadecimal` or `octal` number representations.

**Returns**

- `int` represented by the `String`

**Code snippet**

```
<pre class="wp-block-code">```
int result = Integer.decode("500");
```
```

**Exceptions to Handle**

[NumberFormatException](https://docs.oracle.com/javase/7/docs/api/java/lang/NumberFormatException.html) will be thrown by `Integer.decode(String s)` in following scenarios.

- If the `String` is null or empty
- If the `String` contains any characters other than integers. Except the ‘-‘ sign which can be used to denote the negative number.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

`String` to `int` conversion is one of the commonly used operation when handling lot of user inputs. With `Java` evolving continuously, there are number of methods available to convert `String` to `int` or `String` to `Integer` object.

In this tutorial, You’ve learnt all the methods available to convert `String` to `int` in Java.

Feel free to comment if you have any questions or feedback.