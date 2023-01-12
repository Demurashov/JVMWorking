# JVMWorking

## `public class JvmComprehension {` 
*//загрузка класса в JVM в следующем порядке: Bootstrap ClassLoаder->Planform ClassLoader->Application ClassLoader в Metaspase(метаданные класса)*

### `public static void main(String[] args) {`
*//подгружается при загрузке класса JvmComprehension, создается фрэйм метода «main» в стэке*
#### `int i = 1;`                      
*// 1  примитив создается во фрэйме метода «main»*
#### `Object o = new Object();`        
*// 2  создается новый объект в «heap» ссылка на этот объект создается во фрэйме метода «main» и присваивается переменной o*
#### `Integer ii = 2;`                 
*// 3 во фрэйме метода «main» создается ссылка на уже существующий объект « Integer»  в «heap» (поскольку число лежит в диапазоне -128 до 127) и присваивается переменной ii*
#### `printAll(o, i, ii);`             
*// 4 в стэке создается новый фрэйм метода printAll*
#### `System.out.println("finished");}`      
*// 7 создается объет строки "finished", через неявный вызов метода toString. В стэке создается новый фрэйм метода «println»,  в который передается ссылка на объект строки. Печатается строка "finished". После чего фрэйм уничтожается со всеми данными. Объект остается в «heap» до сборщика мусора.*
    
### `private static void printAll(Object o, int i, Integer ii) {`
//4  в метод передаются значения переменных o,i,ii, в случае переменной o -ссылка на объект
#### `Integer uselessVar = 700;`                   
// 5 создается новый объект «Integer со значением 700 в «heap»,  во фрэйме метода «print all» создается ссылка на объект и присваивается переменной uselessVar
#### `System.out.println(o.toString() + i + ii); `
// 6 создается новый объект типа String в «heap». Затем в стэке создается новый фрэйм метода «println»,  туда передаются значения переменных и ссылка на объект строки. Печатается строка, содержащая ссылку на объект Object и значения i и ii, преобразованные в строки неявным вызовом метода toString.  После окончания работы метода фрэйм уничтожается. После окончания работы метода фрэйм уничтожается вместе со всеми данными. Объекты остаются в «heap», до запуска сборщика мусора. Те объекты, на которые не окажется ссылок ни в одном фрэйме или другом объекте будут уничтожены.

