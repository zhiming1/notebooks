---
layout: post
title: 常见算法
categories: [冒泡排序,插入排序,快速排序]
description: php排序算法,冒泡排序,插入排序,快速排序
keywords: php排序算法,冒泡排序,插入排序,快速排序
---

# 常见算法

## 冒泡排序
```php
function bubbling($list) {
    $count = count($list);
    if ($count <= 1) return $list;
    for ($i = 1; $i < $count; $i++) {
        for ($j = 0; $j < $count - $i; $j++) {
            if ($list[$j] > $list[$j + 1]) {
                $temp = $list[$j];
                $list[$j] = $list[$j+1];
                $list[$j+1] = $temp;
            }
        }
    }
    return $list;
}
```
## 插入排序
```php
function insertSort($list) {
    $count = count($list);
    for ($i = 1; $i < $count; $i++) {
        $temp = $list[$i];
        $j = $i-1;
        while ($j >= 0 && $list[$j] > $temp) {
            $list[$j+1] = $list[$j];
            $j--;
        }
        
        if ($i != $j+1) 
            $list[$j+1] = $temp;
    }
    return $list;
}
```

## 快速排序
```php
function quickSort($list) {
    $count = count($list);
    if ($count <= 1) return $list;
    
    $right = [];
    $left = [];
    for ($i = 1; $i < $count; $i++) {
        $ref = $list[0];
        if ($list[$i] > $ref) {
            $right[] = $list[$i];
        }
        if ($list[$i] < $ref) {
            $left[] = $list[$i];
        }
    }
    $leftList = quickSort($left);
    $rightList = quickSort($right);
    return array_merge($leftList, [$ref], $rightList);
}
```