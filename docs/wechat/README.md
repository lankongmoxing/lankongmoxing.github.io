# 微信小程序 代码风格

## wxml

- {{}}内使用单个变量

`<view>{{ text }}</view>`

`<image src="{{ src }}"></image>`

- {{}} 内使用多个变量

`<view>{{ text || text2 }}</view>`

- {{}} 内不能有复杂的逻辑

`<view>{{ text }}</view>`
