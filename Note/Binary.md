
二进制是计算机中储存和处理数据所采用的数位系统，这是因为数字电路可以表达开和关两种方式，这可以很好的对应数字系统的 0 和 1。通过十进制我们可以看出，十进制中的个位表达的是 10 的 0 次方，十位位表达的是 10 的 1 次方，百位表达的是十的 2 次方，如果我们有一个数字，321，我们可以用 3 * 10 的二次方 + 2 * 10 的 1 次方 + 1 乘以 10 的 0 次方。

以我们生活中的红绿灯为例（没有黄灯的情况下）红灯代表可以不能通行，而绿灯代表可以通行。 

我们不妨大开脑洞设想一下，如何表示道路的更多种状态。比如提醒行车马上就要从红灯变成绿灯，以及重要国家领导出行，所有道路上的行车立即停止？
我们可以再增加一组红绿灯，为了更方便的表达，我们对“双红绿灯”进行编码，红灯用 0 表示，绿灯用 1 表示，

	00 ,红红灯, 代表两个都是红灯, 代表重要领导出行, 所有车道都不能通行
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202311022341874.png)



	那么  01 ,红绿灯,代表车辆不能通行

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202311022337963.png)
	11, 绿红灯，也代表警示灯，代表车灯马上就要变化

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202311022342475.png)


	11,双绿灯，代表车辆可以通行

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202311022344024.png)


## 32 位的 int 类型数据最大能表示多少数据？



