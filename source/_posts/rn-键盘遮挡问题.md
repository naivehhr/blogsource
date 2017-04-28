---
title: rn-键盘遮挡问题
date: 2017-03-28 22:35:37
tags:
---

# rn-键盘遮挡问题
***
1、KeyboardAvoidingView
2、DeviceEventEmitter(隐藏API系列)
<!--more-->
```javascript
 constructor (props){
    super(props);
    DeviceEventEmitter.addListener('keyboardWillShow', this.keyboardWillShow.bind(this));
    DeviceEventEmitter.addListener('keyboardWillHide', this.keyboardWillHide.bind(this));
  }

  keyboardWillShow (e){
    this.commentView && this.commentView.setNativeProps({
            style: {
                height: commentHeight - e.endCoordinates.height
            }
        })
  }

  keyboardWillHide (){
    this.commentView && this.commentView.setNativeProps({
            style: {
                height: commentHeight
            }
        })
  }  

 componentUnMount(){
    this.keyboardWillHideEvent.remove()
    this.keyboardWillShowEvent.remove()
  }

```

>  
> 描述

