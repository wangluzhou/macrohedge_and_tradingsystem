## 因子事件表

### 元事件

| 因子事件代码 | 事件值类型 | 具体描述 | 关键参数 |
| :--- | :--- | :--- | :--- |
| e000 | 数值 | 因子值与阈值差 | 阈值H |
| e001 | 数值 | 因子值大于过去N个周期的均值和M倍标准差的和 | 历史时间窗口值N |
| e002x1 | 布尔类型 | 连续N个周期上涨超过H | 时间窗口N，涨幅阈值H |
| e002x2 | 布尔类型 | 连续N个周期下跌超过H | 时间窗口N，跌幅阈值H |
| e003x1 | 布尔类型 | 反转，连续N个周期上涨后出现下跌 | 时间窗口N，下跌阈值H |
| e003x2 | 布尔类型 | 反转，连涨N个周期后下跌后出现上涨 | 历史时间窗口N，上涨阈值H |
| e004 | 数值 | 因子过去N个周期的总涨\(跌\)幅-上涨\(下跌\)阈值 | 历史时间窗口N, 上涨阈值H |
| e005 | 布尔类型 | 超过一定的阈值H持续N个周期 | 持续时间N,阈值H |
| e006 | 数值 | M周期均线和N周期均线的差，判断趋势 | 周期数M和周期数N |
| e007 | 数值 | RSI：N日RSI=\[A÷\(A+B\)\]×100%；公式中，A——N日内收盘涨幅之和；B——N日内收盘跌幅之和\(取正值\)；N日RSI=100-100/\(1+RS\) | 历史时间窗口N |

### 因子事件配置格式

* relation 确定正向关系还是负向关系
* type 确定信号端在哪边

```json
{
    "060E.CS": {
        "cm": {
            "e000":
                {
                    "period":5,
                    "relation":POSTIVE,
                    "type": UP,
                    "threshold": 0.05
                },

            "e001":
                {
                    "period": 1,
                    "relation": POSTIVE,
                    "type": ALL,
                    "his_count": 30,
                    "std_count": 0

                },
            "e002":
                {
                    "period": 5,
                    "relation": POSTIVE,
                    "type": UP,
                    "his_count": 3,
                    "threshold": 0.01
                },
            "e003":
                {
                    "period":5,
                    "relation": NEGATIVE,
                    "type": DOWN,
                    "his_count":3
                },
            "e004":
                {
                    "period":5,
                    "relation":POSTIVE,
                    "type":UP,
                    "his_count": 30,
                    "threshold": 0.01
                },
            "e005":
                {
                    "period": 5,
                    "relation": POSTIVE,
                    "type": UP,
                    "his_count": 30,
                    "threshold": 0.01
                },
            "e006":
                {
                    "period": 5,
                    "relation": POSTIVE,
                    "type": UP,
                    "long_count": 30,
                    "short_count": 5,
                    "std_count": 1

                },
            "e007":
                {
                }

        }
    }

}
```



