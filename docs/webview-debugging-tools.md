# WebView 调试工具

## 调试示例代码

为了帮助诊断 WebView 元素高亮问题，我们提供了一系列调试函数。这些函数可以帮助您：

1. 检查 sourceJSON 数据结构
2. 测试坐标解析逻辑
3. 模拟元素过滤过程
4. 验证 WebView 坐标注入
5. 测试 HTML 源码解析

## 使用方法

### 在浏览器开发者工具中

1. 复制 `/tmp/docs/webview-debugging-examples.js` 文件内容到控制台
2. 运行 `runCompleteDebugging()` 查看完整调试流程
3. 或单独运行特定函数进行针对性调试

### 常见调试场景

- **WebView 元素不显示**: 运行 `debugSourceJSON()` 检查坐标数据
- **位置偏移问题**: 使用 `simulateWebViewCoordinateInjection()` 验证坐标计算
- **元素被错误过滤**: 通过 `simulateElementFiltering()` 检查过滤逻辑
- **HTML 解析问题**: 用 `testHtmlSourceParsing()` 验证源码识别

### 在 Appium Inspector 代码中集成

1. 在相关文件中添加必要的调试代码
2. 在适当的位置调用调试函数检查数据
3. 使用控制台输出验证处理步骤

## 调试函数说明

### debugSourceJSON(sourceJSON)
检查源码数据结构，识别缺少坐标信息的元素和 WebView 特有属性。

### testCoordinateParsing()
测试不同格式的坐标解析，验证 Android bounds 格式和 iOS 独立属性格式的处理。

### simulateElementFiltering()
模拟元素渲染过滤逻辑，对比原始过滤逻辑和改进后的过滤逻辑。

### simulateWebViewCoordinateInjection()
模拟 WebView 坐标注入过程，测试不同平台配置的处理结果。

### testHtmlSourceParsing()
测试 HTML 源码解析逻辑，验证源码类型识别的准确性。

### runCompleteDebugging()
运行完整的调试流程，综合检查所有处理环节。

## 注意事项

- 调试函数仅用于开发和诊断，不应在生产环境中使用
- 某些函数会输出大量日志信息，建议在需要时才运行
- 如需要实际的调试代码，请参考 `/tmp/docs/webview-debugging-examples.js`