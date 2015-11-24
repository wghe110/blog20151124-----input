#移动端输入框样式
 - 在移动端，我们公司通过输入框主要收集用户的姓名和电话，以下是对输入框获取焦点时，控制弹出键盘的样式来增强用户体验。

###输入姓名
<<<<<<< HEAD
- 我们的用户都是中国人，输入用户名为中文，所以弹出键盘是输入中文状态即可，这个时候type = 'text'即可，默认状态下一般都是弹出中文输入键盘，所以  
<input type="text">
- 可满足
---
###输入电话/手机  
- 这个需要输入数字，所以我们希望它获取焦点时可以弹出数字键盘，第一想到的是把type设置为number，但是在type=number时输入框的右侧会出现两个小按钮，丑丑的，而且点击还可输入负数，用户体验不好。
- 所以我们尝试用样式来去掉这两个小按钮，我们设置webkit的-webkit-inner-spin-button属性以及-webkit-outer-spin-button属性，都设置为-webkit-appearance: none即可。大概样式是这样的  
=======
    我们的用户都是中国人，输入用户名为中文，所以弹出键盘是输入中文状态即可，这个时候type = 'text'即可，默认状态下一般都是弹出中文输入键盘，所以<input type="text">可满足

###输入电话/手机
    这个需要输入数字，所以我们希望它获取焦点时可以弹出数字键盘，第一想到的是把type设置为number，但是在type=number时输入框的右侧会出现两个小按钮，丑丑的，而且点击还可输入负数，用户体验不好。 
    所以我们尝试用样式来去掉这两个小按钮，我们设置webkit的-webkit-inner-spin-button属性以及-webkit-outer-spin-button属性，都设置为-webkit-appearance: none即可。大概样式是这样的
>>>>>>> origin/master

    类名::-webkit-inner-spin-button {
        -webkit-appearance: none;
    }
    类名::-webkit-outer-spin-button {
        -webkit-appearance: none;
    }

- 这样可以去掉两个小按钮，但这样一个一个设置太麻烦，所以第二种修改方案是：

    input[type='number']::-webkit-outer-spin-button,
    input[type='number']::-webkit-inner-spin-button {
        -webkit-appearance: none;
    }

- 这样是不是就ok了呢？应该是ok的，但是当我们需要type=number的两个小按钮时（还没遇到过），还必须还原回来！所以感觉这种全局重置样式不怎么好。

- 在网上看到一个方法
    <input type="tel">
- 这个方法可以很好的替换type="number"的方法，而且手机端兼容性很好。

---
###总结
- 在用input来收集用户信息时：
- **姓名输入用text即<input type="text">**
- **电话/手机输入用text即<input type="tel">**

