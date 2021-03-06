
## 给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。
> 给定 nums = [2, 7, 11, 15], target = 9 返回 [0,1]

```javascript 1.8
let nums = [2, 7, 11, 15],
    target = 9;
```

### 暴力求解法
> 时间复杂度 O(n²)、空间复杂度 O(1)
```javascript 1.8
let twoSum = function (nums, target) {
    for (let i = 0, len = nums.length; i < len; i++) {
        let item = nums[i];
        //此处需要指定indexOf检索的起始位置
        let index = nums.indexOf(target - item,i+1);
        if(~index){
            return [i,index]
        }
    }
};
```

### 使用哈希表的方式（需考虑数组元素不发生重复）
> 时间复杂度 O(n)、空间复杂度 O(n)
```javascript 1.8
let twoSum = function (nums,target) {
     let map = new Map();
     for(let i = 0,len = nums.length; i<len;i++){
         if(map.has(target - nums[i])){
             return [map.get(target - nums[i]),i]
         }
         map.set(nums[i],i);
     }
 };
```