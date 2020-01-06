# You must not call setTag() on a view Glide is targeting

- 方法一

	https://blog.csdn.net/u010899537/article/details/74394642

- 方法二

	不使用setTag（Object tag)方法进行设值，改用setTag(int key,Object tag);
	
	注意 key 不能为随便的 int 值，详情查看：
	https://blog.csdn.net/yanxiaosa/article/details/54926264 