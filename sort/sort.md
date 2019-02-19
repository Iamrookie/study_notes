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