---
title: 编程语言面试题之文件API和递归考察
date: 2020-10-27 18:47:06
tags:
---
**简介：常见的文件API掌握，和递归算法的熟悉**

- 考点: 文件API使用，简单递归逻辑代码编写、代码编写规范，简洁性
- 难度【** **】
- 代码编写需求： 找出某目录下的所有子目录以及子文件并打印到控制台上

```

    public static void main(String[] args) {

        //找出某目录下的所有子目录以及子文件并打印到控制台上
        List<String> paths = new ArrayList<>();

        getAllFilePaths(new File("/Users/xdclass/Desktop/小滴课堂-架构面试题教程/demo"),paths);

        for(String path : paths){
            System.out.println(path);
        }


    }

    private static void getAllFilePaths(File filePath, List<String> paths) {

        File[] files =  filePath.listFiles();
        if(files == null){
            return;
        }
        for(File f : files){
            if(f.isDirectory()){
                paths.add(f.getPath());
                getAllFilePaths(f,paths);
            }else{
                paths.add(f.getPath());
            }
        }
    }

```