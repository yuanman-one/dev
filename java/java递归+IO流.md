java的递归
    递归，是某一个类的一个方法重复去调用自身的一个循环过程
        1、该方法一定要传递参数
        2、有return 返回数值
        3、有if判断，且回调自身
        
java的IO流
       Input:输入或者读取
       
       Output:输出或者写入
       
       Stream：流    具有方向性。
       
  文件流：对已经存在的文件的内容进行操作，所以是对内容操作而不是对文件属性进行操作
      
      按照读取类型方式分为：字节流（8位0000 0000），
                                          字符流（16位）
       按照流动的方式分为：输入流（读取流）、输出流（写入流）
字节流
       FileInputStream fis =
       FileOutputStream fos =
       
 字符流
       FileReader
       BufferReader  缓冲
       FileWritter
       BufferWritter  缓冲
       
       String  StringBuffer     StringBuilder
       String：final数据类型，线程安全，但消耗内存大
       StringBuffer：字符串缓存，可以任意对内容修改，但线程非安全
       StringBuilder：字符串缓存，可以对任意内容修改，单线程安全
对象流
      1、是一个高级流、可以方便的读取java中的任何对象
          注意：高级流是不能单独存在的，是依赖于其他低级流而存在的
      2、对象序列化：将对象转换为一个字节序列进行写入文件中（输出）
           对象反序列化：将一个字节序列 转化为对应的对象进行从文件中读取对象  （输入）  
      3、对象输出流ObjectOutputStream
      3.1、用来将对象进行序列化的输出流
      3.2、构造方法
                ObjectOutputStream(OutputStream out)
                创建写入指定 OutputStream 的 ObjectOutputStream。
       3.3、 常用方法
                writeObject(Object obj)：将给定的对象转换为一组字节，
                                                      然后将该组字节通过其连接的流写出
                      将指定的对象写入 ObjectOutputStream。
               注意：（1）此流在针对对象进行序列化时，必须要求序列化的对象所属的类型
                        必须实现Serializble接口，
                        实现此接口不需要重写任何方法，此接口的目的主要是为了
                        提供一个常量serialVersionUID,表明该类默认serialVersionUID，
                        但不同平台编译器实现有所不同，所有若想跨平台都应显示声明版本号       
                       （2）对象在序列化后得到的字节序列往往比较大，有时我们在对于一个
                       对象进行序列化时，可以忽略某些不必要的属性，从而对序列化后得到
                       的字节序列“瘦身”，使用transient，被该关键字修饰的属性在序列化时
                       ，其值将被忽略
       4、对象输入流ObjectInputstream
       4.1、用来将对象进行反序列化的输入流
       4.2、构造方法
       	ObjectInputStream(InputStream in)
          创建从指定 InputStream 读取的 ObjectInputStream。  
       4.3、常用方法
           readObject()：可以从流中读取字节并转换为对应的对象
          从 ObjectInputStream 读取对象。
                        
             
                对象：
                       创建对象
                       1、定义一个类
                class  类名｛       
                       修饰符 变量类型  变量名称1；
                       修饰符 变量类型  变量名称2；
                       ………………
                       //成员方法
                       修饰符   返回值类型  方法名称（参数列表）｛
                                             方法体；
                       ｝
                       ………………
                 ｝ 
               注意：类名建议首字母大写
               eg：定义一个人类，属性name，age，sex，address，行为eat，sleep
                 
                 2.如歌创建对象
                 类名 引用变量名称 = new 类名（）；
                 
           访问对象中的成员      
                  引用变量名称.成员
                  注意：当类中的成员变量用private修饰，此时不能通过“引用变量名称.成员变量”
                  的方式进行访问成员变量，此时可以通过构造方法和setXXX().getXXX()声明的
                  属性进行赋值或者获取成员变量值
               
               
               
               
 在一个文件中可以存在多个类，类和类之间是相互独立的，
 但是只能存在一个public所修饰的类，并且此类必须与文件同名
 
               
            
    
                
                
                
                
                
                
                
                
                
                
                
                
                
                
                
                
                
                
                
       
       