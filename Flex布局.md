# Flex 布局

flex的概念最早是在2009年被提出，目的是提供一种更灵活的布局模型，使容器能通过改变里面项目的高宽、顺序，来对可用空间实现最佳的填充，方便适配不同大小的内容区域。

```
.container {
    display: flex;
}
```

## Container 属性

```
display:            flex;
```

```
flex-direction:     row（默认值） | row-reverse | column |column-reverse
```

```
flex-wrap:          nowrap（默认值） | wrap | wrap-reverse
```

```
justify-content:    flex-start（默认值） | flex-end | center |space-between | space-around | space-evenly
```

```
align-items:        stretch（默认值） | center  | flex-end | baseline | flex-start
```

```
align-content:      stretch（默认值） | flex-start | center |flex-end | space-between | space-around | space-evenly
```

## Item 属性

```
order:              0（默认值） | <integer>
```

```
flex-shrink:        1（默认值） | <number>
```

```
flex-grow:          0（默认值） | <number>
```

```
flex-basis:         auto（默认值） | <length>
```

```
flex:               none | auto | @flex-grow @flex-shrink @flex-basis
```

```
align-self:         auto（默认值） | flex-start | flex-end |center | baseline| stretch
```
