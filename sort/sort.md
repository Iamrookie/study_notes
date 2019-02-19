# study_notes
排序算法：
1.冒泡排序：

原理：依次比较数组相邻的两个数，然后左边大的就交换，否则不交换，执行完第一轮最大的数会排到数组的末尾，执行完第二轮第二大的数会被换到末尾第二位处，依次如下到最后都有序。即大数往下沉。

coding：

public void bubble(int a[]){

//数组为空或数组只有一个数

if(a == null || a.length < 2){return;}

for(int end = a.lentgh-1 ; end > 0 ; end —){

​     for(int i = 0; i < end; i++){

​          if(a[i] > a[i+1]){

​              swap(a , i , i+1);

​             }

​          }

​     }

}



//交换数组的两个数

public void swap(int a[] , int i, int j){

 int temp = a[i];

 a[i] = a[j];

 a[j] = temp;

}



2.选择排序

原理：从数组的0到N-1位置找出一个最小的数放到0位置，然后从1到N-1位置找出一个最小的书放到1位置，依次进行下去。

coding：

```
public static void selectionSort(int a[]) {
        if (a == null || a.length < 2) return;

        for (int i = 0; i < a.length; i++) {
            int minIndex = i;
            //不写j=i，为了后面j的判断不越界
            for (int j = i + 1; j < a.length; j++) {
                minIndex = a[j] > a[j - 1] ? j - 1 : j;
            }
            swap(a, i, minIndex);
        }
    }
}
```

3.插入排序

原理：从数组的1位置开始(0位置就一个数字没人跟他比，默认已经有序)，1位置跟0位置比，0位置大，就交换0与1上的数，后续是2位置与1比然后1与0位置比，依次进行比较，就好比玩斗地主牌按小到到放，当拿到一张牌，依次跟左边的比较放到合适的位置。

coding:

```
public static void insertSort(int a[]) {
    if (a == null || a.length < 2) return;

    for (int i = 1; i < a.length; i++) {
        for (int j = i - 1; j >= 0 && a[j] > a[j + 1]; j--) {
            swap(a, j, j + 1);
        }
    }
}
```