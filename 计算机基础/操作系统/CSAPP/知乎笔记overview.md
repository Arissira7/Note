### 关于本书

《深入理解计算机系统》——简称[CSAPP](https://zhida.zhihu.com/search?content_id=189255462&content_type=Article&match_order=1&q=CSAPP&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3ODI4MTEzNjksInEiOiJDU0FQUCIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjE4OTI1NTQ2MiwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.jxqgOtiICdiC0bF1lelOAHcsRKO9pPwZh4a_ZccMdtg&zhida_source=entity)，被称为计算机领域的圣经，豆瓣评分9.8。对这本书的各种夸赞太多了。我当初也是因为看到了那么多对此书的盛赞，最后选择花时间好好学了一下。

书的情况就不多讲了，直接放一下豆瓣的链接吧。

[深入理解计算机系统](https://link.zhihu.com/?target=https%3A//book.douban.com/subject/26912767/)

**此书适合对象**

这本书适合刚入门计算机领域的人，尤其是非计算机科班的同学（比如我），最好要有一点点的知识基础（一点点就行），对已经有很深的计算机基础的人也不太适合。这本书就是以一种大杂烩的方式讲解了计算机系统中各个层面的知识，涵盖范围比较广，同时作者也把知识讲得很透彻。但是由于篇幅所限，某些地方不可避免地还是讲得有些粗浅，比如最后两章关于网络编程和并发编程的部分。

### 对此书的总体感受

能够增加知识底蕴的一本书，我在开始看这本书的时候还是一个小白，那时候刚学了一点点C++，什么编译链接都只知道个名字，计算机领域在我面前好像整个全是一片雾。然后看的时候感觉好像在学许多不怎么会用到的知识，但是学习的过程中却又不知不觉间明白了很多东西，时不时有种豁然开朗的感觉：原来我曾经遇到的问题跟这个有关啊，原来程序运行是这样实现的啊，原来xxx，等等。学完后当然不能说那片雾就没了，但是确实退散了许多，程序出了问题也不再像以前那样一头雾水。

### 我的学习方式

TODO。

我对各种技术书的学习方式其实大同小异，就不再每本书都专门讲了，后面写一篇关于学习方式的文章，到时直接把链接插进来吧。

### 关于本笔记

本笔记目前已包含 CSAPP 中除第四章（处理器部分）外的其他各章节，但部分章节的笔记尚未整理完全。未整理完成的部分包括：ch3、ch11、ch12 的后面几小节；ch5 的大部分。

我在整理笔记时所考虑的是：在笔记记完后，当我需要查找某个知识点时，不需要到书中去找，只需查看笔记即可找到相关知识点。因此在整理笔记时力求全面与简洁，能够在查找时快速找到并迅速理解。在此基础上，笔记已整理的内容是对书中内容的提炼，包括了我在学习时所认为的书中所有有用的知识点，因此每章的笔记内容都比较多。

笔记内容总共6万3千多字。

### **笔记适用对象**

看过一遍《深入理解计算机系统》，可以查看本笔记对学习内容进行复习和梳理。

正在看《深入理解计算机系统》，自己没有精力或不想记笔记，可以每看完一章书籍，再看一遍笔记以梳理学习内容。

需要查阅《深入理解计算机系统》内的知识点，可以通过本笔记查阅。

### **笔记不适合的对象**

本笔记不能完全成为《深入理解计算机系统》的代替品，笔记中仅包含对《深入理解计算机系统》中本人认为所需要整理的内容的提炼与部分代码示例。

### 笔记目录

[1 计算机系统漫游](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D7147b6236213e667ab56314fbf660282%26sub%3DE74BA6BA8D774C0391AECEE74BB24633)

**第一部分 程序结构和执行**

[2 信息的表示和处理](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D837cb22416d53a79df8aa3c5d1f5ede3%26sub%3D724CD8FEA5A84486BCA476840C075C64)

[3 程序的机器级表示](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3Dfc45065e632e1d7a6f07ab4b11152fbe%26sub%3D50F12663867942C7899239A0390D1ED9)

[5 优化程序性能](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D1437a754ae216e1037a8601014611115%26sub%3DCCB6C588FB6842F9B2259F05E4BDF7FA)

[6 存储器层次结构](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D1cbaebb119458e1d6043099a42e3db7c%26sub%3DFAB10C3E540248FDB0D992A479706B7C)

**第二部分 在系统上运行程序**

[7 链接](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D5e526b82c207a6410dac32075eebe283%26sub%3D5002EBC675B047F4857F409790A76969)

[8 异常控制流](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3Da7598023e32c815dda65a7aebbcad03b%26sub%3DEE5AE16AFC304C8BAFD9521A0CBB470C)

[9 虚拟内存](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D571afc0df48bcc5faedf009f92ea125d%26sub%3D3BCC0BECB6A44892BB2FD58905EE12A6)

**第三部分 程序间的交流和通信**

[10 系统级IO](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3Df227ad68c05891737bde374e977b5dd7%26sub%3DFBF08934F9734340987E9EB9CEC187D4)

[11 网络编程](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D9d4a7967bd864a75eac689866aa19533%26sub%3DA14C7CD927C74C29810CAB61C90953C3)

[12 并发编程](https://link.zhihu.com/?target=http%3A//note.youdao.com/noteshare%3Fid%3D2c486be56b632f5557328e40581c5e2b%26sub%3DBE965181FEF84841A79FBBD41A79E945)

第 11、12 章的笔记都不全，预计可能不会再补了。第 11 章主讲网络编程，第 12 章主讲并发编程，以多线程编程为主，但是两章都太简略了，如果要学的话，推荐直接去看《TCPIP网络编程》、[《Linux高性能服务器编程》](https://zhida.zhihu.com/search?content_id=189255462&content_type=Article&match_order=1&q=%E3%80%8ALinux%E9%AB%98%E6%80%A7%E8%83%BD%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%BC%96%E7%A8%8B%E3%80%8B&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3ODI4MTEzNjksInEiOiLjgIpMaW51eOmrmOaAp-iDveacjeWKoeWZqOe8lueoi-OAiyIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjE4OTI1NTQ2MiwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.Ae0JJt_q4Xtkr96fF5d1fRQ_gEq0IuZbXjZ6AVkIamg&zhida_source=entity)，或APUE、UNP等书（对于像我这样转方向自学的同学，我更推荐前两本）。

### 导航

下面是我发的各类技术文章的导航：

[https://zhuanlan.zhihu.com/p/553465759](https://zhuanlan.zhihu.com/p/553465759)