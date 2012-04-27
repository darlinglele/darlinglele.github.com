---
layout: post
title: "clean code notes"
description: ""
category: 
tags: []
---
Try/Catch 代码块经常破坏了代码的结构，把正常错里和错误处理混为一谈。因此应当把错误处理单独处理，放在一个单独的方法里，并却这个方法仅仅做错误处理一件事情。在这样的方法里try应当是第一个单词，并且catch/finaly 后面也不该有其他的内容。
   public void delete(){
     try{
          deletePage();
      }
    catch{
          logError();
      }
  }

public void deletePage(){
    .....
    .....
}
在上面例子中delete只做与错误处理相关的事情，忽略了deletePage的逻辑。 deletePage也只处理删除页面的逻辑，忽略了错误处理相关的事情。这样美妙的隔离更容易理解和修改。
{% include JB/setup %}
