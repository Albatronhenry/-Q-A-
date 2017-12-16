写代码使得分别出现`StackOverflowError`和`OutOfMemoryError`

 1. StackOverflowError

　　堆栈溢出错误一般是递归调用嘛。下面的代码就可以出现：
```
package T20161009;
public class StackOverflowTest {
public static void main(String[] args) {
		method();
	}
public static void method(){
		for(;;)
		method();
	}
}
```
　　


 2. OutOfMemoryError

　　内存溢出一般是出现在申请了较多的内存空间没有释放的情形。下面的代码就可以出现：
```
package T20171009;
import java.util.ArrayList;
import java.util.List;
public class OutOfMemoryTest {
public static void main(String[] args){
		List list=new ArrayList();
		for(;;){
			int[] tmp=new int[1000000];
			list.add(tmp);
		}
	}
}
```
