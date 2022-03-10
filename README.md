# Java List排序 基本語法

## Sort 排序
```
package cyber;

import java.util.*;
import java.lang.*;
import java.io.*;

// 一個Book的類
class Book
{
    Integer bookID;
    String name, type;

    // Constructor
    public Book (int bookID, String name,
                 String type)
    {
        this. bookID = bookID;
        this.name = name;
        this. type = type;
    }

    // Book的資料
    public String toString()
    {
        return this. bookID + " " + this.name +
                " " + this. type;
    }
}

class BookSort implements Comparator<Book>
{
    //以book的ID升序排列
    public int compare(Book a, Book b)
    {
        return b.name.compareTo(a.name);
    }
}

class Main
{
    public static void main (String[] args)
    {
        ArrayList< Book > list3 = new ArrayList<Book>();
        list3.add(new Book (1234, "AGogogo", "computer"));
        list3.add(new Book (1698, "eHappy", "art"));
        list3.add(new Book (5468, "DMartin", "music"));

        System.out.println("Unsorted");
        for (int i=0; i< list3.size(); i++)
            System.out.println(list3.get(i));

        Collections.sort(list3, new BookSort());

        System.out.println("\nBook Sort");
        for (int i=0; i< list3.size(); i++)
            System.out.println(list3.get(i));
    }
}
```    

## Sort 排序2
```
package cyber;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class ListSort {

    public static class StringIntPair{

        private String string;
        private int integer;

        public StringIntPair(String s, int i) {
            string = s;
            integer = i;
        }

        protected String getString() {
            return string;
        }

        protected int getInteger() {
            return integer;
        }

        public String toString() {
            return string + "\t" + integer;
        }
    }

    public static void main(String[] args) {

        List<StringIntPair> list = new ArrayList<StringIntPair>();

        list.add(new StringIntPair("ab", 5));
        list.add(new StringIntPair("ca", 3));
        list.add(new StringIntPair("aa", 2));
        list.add(new StringIntPair("db", 4));
        list.add(new StringIntPair("bc", 1));

        System.out.println("排序前");
        for (Object o:list) {
            System.out.println(o);
        }

        // 依string排序
        Collections.sort(list,
                new Comparator<StringIntPair>() {
                    public int compare(StringIntPair o1, StringIntPair o2) {
                        return o1.getString().compareTo(o2.getString());
                    }
                });
        System.out.println();
        System.out.println("依string排序");
        for (Object o:list) {
            System.out.println(o);
        }

        // 依Integer排序
        Collections.sort(list,
                new Comparator<StringIntPair>() {
                    public int compare(StringIntPair o1, StringIntPair o2) {
                        return o2.getInteger()-o1.getInteger();
                    }
                });
        System.out.println();
        System.out.println("依Integer排序");
        for (Object o:list) {
            System.out.println(o);
        }
    }
}
```

## Remainder
```
package cyber;

public class pa {

    static void algo(int start, int end, int interval,int divisor,int remainder ){
        StringBuilder sb = new StringBuilder(100);
// 0~100 1 0.....100
        for(int i = start; i<= end ; i+= interval){
            if(i%divisor==remainder){
               sb.append(i+",");
            }
        }
        System.out.println(sb.substring(0,sb.length()-1).toString());

    }

    public static void main(String[] args) {
        algo(0,100,1,10,1);
    }
}
```
                                 
## Time
```
public class time {
    static void time(int days){
        SimpleDateFormat sdf=new SimpleDateFormat("yyyy/MM/dd");
        Calendar rightNow = Calendar.getInstance();
        rightNow.add(Calendar.DAY_OF_YEAR,days);
        Date dt1=rightNow.getTime();
        String reStr = sdf.format(dt1);
        System.out.println(reStr);
    }

    public static void main(String[] args) {
        time(5);
    }
}
```

## Phone
```
package cyber;

public class phone {
    static void phonecheck(String phone){
        if(phone.substring(0,2).equals("09") && phone.length()==10){
            System.out.println("OK");
        }else {
            System.out.println("Not OK");
        }
    }

    public static void main(String[] args) {
        phonecheck("0981712612");
        phonecheck("0481712612");
        phonecheck("098171261");
    }
}
```

## TwoSum

```
package cyber;
public class TwoSum {
    static int[] TwoSum(int[] abc,int target){
        int[] result = new int[2];
        for(int i =0 ; i <= abc.length ; i++){
            for(int j = i + 1 ; j <= abc.length-1 ; j++){
                if(abc[i] + abc[j] == target){
                    result[0] = i;
                    result[1] = j;
                }
            }
        }
        return result;
    }

    public static void main(String[] args) {
        int[] efg= new int [] {3,4,7,9,11};
        System.out.println( TwoSum(efg,10)[0]);
        System.out.println( TwoSum(efg,10)[1]);
    }
}

```

## Reference
[time](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/313272/)
[twosum](https://woooooooooord.wordpress.com/2016/11/14/leetcode-1-two-sum/)
[sqlnull](https://blog.xuite.net/tolarku/blog/27569185)
[stream](https://www.runoob.com/java/java8-streams.html)
[SQL50](https://www.itread01.com/content/1544769369.html)
[Java stream](https://mycollegenotebook.medium.com/java-stream-%E7%AD%86%E8%A8%98-%E4%B8%8A-34df0e282fc8)
[java8 List集合的排序，求和，取最大值，按照条件过滤](https://blog.51cto.com/u_15127525/3921322)
