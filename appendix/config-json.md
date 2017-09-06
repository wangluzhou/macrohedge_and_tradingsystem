### 因子事件配置格式

```json
config = {
    "060E.CS": {
        "cm": {
            "e000":
                {
                    "period":5,
                    "relation":POSTIVE,
                    "type": "up",
                    "his_count": 30,
                    "threshold": 0.05
                },

            "e001":
                {
                    "period": 1,
                    "relation": POSTIVE,
                    "type": "linear",
                    "his_count": 30,
                    "std_count": 0

                },
            "e002":
                {
                    "period": 5,
                    "relation": POSTIVE,
                    "type": "up",
                    "count": 3,
                    "rise_threshold": 0.01
                },
            "e003":
                {
                    "period":5,
                    "type":NEGATIVE,
                    "count":3,
                    "fall": 0.01
                }
        }
    }

}
```



