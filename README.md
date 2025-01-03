# N32G031串口IAP升级代码及应用示例

## 资源描述

本仓库提供了一个基于N32G031主控芯片的串口IAP（In-Application Programming）升级代码及应用示例。该资源包含两个主要部分：

1. **Boot代码**：用于处理通过串口2（PA9和PA10）进行的IAP升级操作。Boot代码负责接收来自电脑端串口工具（如XCOM V2.6.exe）的升级数据包，并将其写入Flash中。

2. **应用代码（App代码）**：这是一个测试应用示例，展示了如何在N32G031上实现简单的功能。应用代码中开启了中断定时器3，并在主程序中每秒打印一条测试数据。

## 功能特点

- **串口IAP升级**：通过串口2（PA9和PA10）进行IAP升级，支持最大包长为128字节的数据传输。
- **数据包格式**：数据包包含包头（0x01 0x01）、报序号（1字节）、长度（1字节）、数据（最大128字节）和尾字节校验和（1字节），最大总包长为133字节。
- **定时器中断**：应用代码中使用了定时器3，每秒触发一次中断，并在中断服务程序中打印测试数据。

## 使用说明

1. **下载资源**：下载本仓库中的压缩文件，解压后包含Boot代码和应用代码。
2. **编译Boot代码**：使用合适的编译工具链编译Boot代码，并将其烧录到N32G031芯片的Flash中。
3. **编译应用代码**：编译应用代码，并将其作为升级数据包通过串口工具发送给Boot代码进行升级。
4. **运行应用**：升级完成后，系统将从Flash中运行应用代码，定时器3将每秒打印一条测试数据。

## 注意事项

- 在进行IAP升级时，请确保串口工具的波特率、数据位、停止位等参数与Boot代码中的配置一致。
- 升级过程中，请勿断电或中断串口通信，以免导致升级失败或系统损坏。

## 联系我们

如有任何问题或建议，欢迎通过GitHub Issues或邮件联系我们。

## 下载链接

[N32G031串口IAP升级代码及应用示例](https://pan.quark.cn/s/9d3dcf9dc857)