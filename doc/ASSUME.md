

obj, til, atz通通生成32位png，如果你需要生成不同格式，需要修改代码。

## MAP（千年地图）

以`start.map`为例
会生成`start`文件夹,在它下面生成如下文件（文件夹）

#### 生成`start.map`,
原有的block格式不要了，(200*200)的地图会直接生成(200 * 200)的地图数据。

````c
struct MAP_CELL{
    int tileId,
    int objId,
    int roofId
    int bMove
}
````

#### 生成`obj`文件夹
所有的物件在这个文件夹下。（ps:打开地图时可以合并，删除物件)

#### 生成`tile`文件夹
原千年地图中的（tile|over）二层设计合为一层, 并且重新生成320 * 240大小的tile图片
所有的(320 * 240)tile图片都会生成一张2/10大小的缩略图，放在mini.jpg中



## ATZ（千年精灵图片)

利用一个简单的二叉树生成一张SpriteSheet(.png)以及记录文件.pos

.pos格式

````c
{
    int count;     //图片数量
    INFO infos[count];
}

struct INFO{
    int x;      //在spriteSheet中的x坐标
    int y;      //在spriteSheet中的y坐标
    int width;  
    int height;
    int px;     //贴图时的偏移
    int py;
}
````
