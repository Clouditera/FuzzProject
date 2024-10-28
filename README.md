# 云起无垠智能模糊测试

云起无垠智能模糊测试平台是一款基于AI的智能模糊测试工具，支持模糊测试全流程自动化测试。本文档主要列举我们在开源项目中测试的项目及测试结果。

## 1. C/C++工程

### 测试结果

| 项目 | 规模 | 覆盖率 | 漏洞 | 测试时长 | 接口数 | 版本(分支、commit、tag) | 更新时间 | 
|-----|-----|-----|-----|-----|-----|-----|-----|
| [yaml-cpp](https://github.com/jbeder/yaml-cpp.git) | 7k | 81.30% |  | 15m | 218/321 | da82fd982c260e7f335ce5acbceff24b270544d1| 2024-10-24 |
| [workflow](https://github.com/sogou/workflow.git) | 37k | 38.05% |  | 15m | 264/762 | efdba8a0e39700242afd40541af0d0ae2b9ee243 | 2024-10-24 |
| [openssl](https://github.com/openssl/openssl.git) | 500k |  |  |  |  | openssl-3.4 | |
| [json-parser](https://github.com/Barenboim/json-parser.git) | 1.7k | |  |  |   | f4f3246110eae35e3ffad5bafc371465b17eb437 ||
| [facil.io](https://github.com/boazsegev/facil.io.git) | 31k |  |  |  |  | 0.7.6 |  |

> 注：规模为项目代码行数，统计方法为调用cloc命令统计出所有的C/C++源代码（包括头文件）并相加。覆盖率表示代码覆盖率，接口数格式为可测试接口数/总接口数，累计测试时长=测试时长*可测试接口数。

### 测试配置
| 项目 | 编译命令 |
|---------|------|
| [yaml-cpp](https://github.com/jbeder/yaml-cpp.git) | mkdir build && cd build<br>cmake -DCMAKE_C_COMPILER=$CC -DCMAKE_CXX_COMPILER=$CXX ..<br>make -j |
| [workflow](https://github.com/sogou/workflow.git) | apt install -y libssl-dev libsnappy-dev<br>mkdir build && cd build<br>cmake -DCMAKE_C_COMPILER=$CC -DCMAKE_CXX_COMPILER=$CXX ..<br>make -j |
| [openssl](https://github.com/openssl/openssl.git) | CC="$CC" ./config && make -j |
| [json-parser](https://github.com/Barenboim/json-parser.git) | make CC=$CC LD=$CC |
| [facil.io](https://github.com/boazsegev/facil.io.git) | |

> 注：$CC、$CXX为云起无垠智能模糊测试平台提供的编译器工具。

### 漏洞列表
| 编号 | 项目 | 描述 | 类型 | 等级 | 版本(分支、commit、tag) | 更新时间 |
|---------|------|---------|------------|---------|---------|---------|