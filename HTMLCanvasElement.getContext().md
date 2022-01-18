# HTMLCanvasElement.getContext()

此方法返回一个 canvas 元素的绘画上下文, 如果不支持此上下文标识, 或者 canvas 已经被设置为不同的上下文模式, 则返回 `null`.

在同一个 canvas 元素上使用相同的 `contextType` 参数多次调用此方法, 会返回同一个绘画上下文实例, 此实例为第一次调用时创建. 在一个 canvas 对象上不能取得不同的绘画上下文对象.

## Syntax

```js
var ctx = canvas.getContext(contextType);
var ctx = canvas.getContext(contextType, contextAttributes);
```

### Parameters

#### contextType

获取不同 canvas 上下文的 `DOMString` 标识, 可能的值有:

* `"2d"`, 会创建一个 `CanvasRenderingContext2D` 对象, 代表一个二维渲染上下文.
* `"webgl"` (或者 `"experimental-webgl"`) 会创建一个 `WebGLRenderingContext` 对象, 代表一个三维渲染环境. 此上下文仅在实现了 WebGL 版本 1 的浏览器上提供.
* `"webgl2"` 会创建一个 `WebGL2RenderingContext` 对象，代表一个三位渲染上下文, 此上下文仅在实现了 WebGL 版本 2 的浏览器上提供.
* `"bitmaprenderer"` 会创建一个 `ImageBitmapRenderingContext`, 其仅提供使用一个使用 `ImageBitmap` 替换 canvas 上下文的能力.

#### contextAttributes

创建渲染上下文可提供几个属性:

2d 上下文属性:

* `alpha`: canvas 是否包含 alpha 通道. 如果设置 false, 这使得浏览器知道背景总是不透明的, 可以加速透明内容和图片的绘制.
* `desynchronized`: 示意浏览器通过将 canvas 绘画循环从事件循环中去同步化, 减少延迟.

WebGL 上下文属性:

* `alpha`
* `depth`
* `stencil`
* `desynchronized`
* `antialias`
* `failIfMajorPerformanceCaveat`
* `powerPreference`
* `premultipliedAlpha`
* `preserveDrawingBuffer`
* `xrCompatible`

### 返回值

一个渲染上下文:

* `CanvasRenderingContext2D`
* `WebGL2RenderingContext`
* `WebGL2RenderingContext`
* `ImageBitmapRenderingContext`

如果 contextType 不符合可选的上下文, 或者与首次 contextType 请求不同, 返回 null.
