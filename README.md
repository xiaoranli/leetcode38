
6、leetcode38.报数
==
解法一：
--  
    外层for:报数第几次 ，内层for:字符串中的每一位记录下重复的字符此时和字符本身，有重复的字符就count++,没有重复就从新字符开始判断。      
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/14 21:44
 * @descriptor  38. 报数
 */
public class CountAndSay_38 {
    //外层for:报数第几次 ，内层for:字符串中的每一位
    //记录下重复的字符此时和字符本身，有重复的字符就count++,没有重复就从新字符开始判断。
    public static String countAndSay(int n) {
        String s = "1";
        for (int i = 2;i <= n; i++) {
            StringBuilder builder = new StringBuilder();
            char c = s.charAt(0);
            int count = 1;
            for (int j = 1; j < s.length(); j++) {
                if(s.charAt(j) == c){
                    count++;
                }else{
                    builder.append(count).append(c);
                    count = 1;
                    c = s.charAt(j);
                }
            }
            s = builder.append(count).append(c).toString();
        }
        return s;
    }

    public static void main(String[] args) {
        String s = countAndSay(4);
        System.out.println(s);
    }
}
</pre>
