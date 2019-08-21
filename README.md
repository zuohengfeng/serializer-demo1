# serializer-demo1
本工程主要是写了几个关于序列化和反序列化的demo，包括了基于java，xml，json，protobuf..

序列化技术的选型
技术层面
1. 序列化空间开销，也就是序列化产生的结果大小，这个影响到传输的性能
2. 序列化过程中消耗的时长，序列化消耗时间过长影响到业务的响应时间
3. 序列化协议是否支持跨平台，跨语言。因为现在的架构更加灵活，如果存在异构系统通信需求，那么这个是必须要考虑的
4. 可扩展性/兼容性，在实际业务开发中，系统往往需要随着需求的快速迭代来实现快速更新，这就要求我们采用的序列化协议基于良好的可扩展性/兼容性，比如在现有的序列化数据结构中新增一个业务字段，不会影响到现有的服务
5. 技术的流行程度，越流行的技术意味着使用的公司多，那么很多坑都已经淌过并且得到了解决，技术解决方案也相对成熟
6. 学习难度和易用性

选型建议
1. 对性能要求不高的场景，可以采用基于 XML 的 SOAP 协议
2. 对性能和间接性有比较高要求的场景，那么 Hessian、Protobuf、Thrift、Avro 都可以。
3. 基于前后端分离，或者独立的对外的 api 服务，选用 JSON 是比较好的，对于调试、可读性都很不错
4. Avro 设计理念偏于动态类型语言，那么这类的场景使用 Avro 是可以的


不同序列化的性能比较：
https://github.com/eishay/jvm-serializers/wiki