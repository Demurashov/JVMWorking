# JVMWorking

1. public class JvmComprehension { *//загрузка класса в JVM в следующем порядке: Bootstrap ClassLoаder->Planform ClassLoader->Application ClassLoader в 
Metaspase(метаданные класса)*
  1. public static void main(String[] args) {*//подгружается при загрузке класса JvmComprehension, создается фрэйм метода «main» в стэке*
  2. int i = 1;                      *// 1  примитив создается во фрэйме метода «main»*
  3. Object o = new Object();        *// 2  создается новый объект в «heap» ссылка на этот объект создается во фрэйме метода «main» и присваивается переменной o*
  4. 
  5. 
