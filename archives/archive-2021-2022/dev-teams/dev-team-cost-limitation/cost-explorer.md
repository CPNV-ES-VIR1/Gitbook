# Cost Explorer

## Sources

* [Cost Explorer - GUI](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-custom-reports.html#save-ce-reports)
* [Cost Explorer - CLI](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ce/index.html)

## Exemple de commande

* [Source](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ce/get-cost-and-usage.html)

```
aws ce get-cost-and-usage --time-period Start=2022-01-01,End=2022-06-30 --granularity MONTHLY --metrics "BlendedCost" "UnblendedCost" "UsageQuantity" --group-by Type=DIMENSION,Key=SERVICE Type=TAG,Key=Environment --filter file://filter.json --profile Vir1_Test
```

```
{
    "Dimensions": {
        "Key": "SERVICE",
        "Values": [
            "Amazon Simple Storage Service"
        ]
    }
}
```

* Exemple de réponse

```
{
    "GroupDefinitions": [
        {
            "Type": "DIMENSION",
            "Key": "SERVICE"
        },
        {
            "Type": "TAG",
            "Key": "Environment"
        }
    ],
    "ResultsByTime": [
        {
            "TimePeriod": {
                "Start": "2022-01-01",
                "End": "2022-02-01"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.0123466541",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.0123466541",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "10493.0925777398",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": false
        },
        {
            "TimePeriod": {
                "Start": "2022-02-01",
                "End": "2022-03-01"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.000765494",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.000765494",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "51.0319401544",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": false
        },
        {
            "TimePeriod": {
                "Start": "2022-03-01",
                "End": "2022-04-01"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.0057114591",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.0057114591",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "2560.0160716728",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": false
        },
        {
            "TimePeriod": {
                "Start": "2022-04-01",
                "End": "2022-05-01"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.006543865",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.006543865",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "3330.1172738641",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": false
        },
        {
            "TimePeriod": {
                "Start": "2022-05-01",
                "End": "2022-06-01"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.0002382",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.0002382",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "55.0000013672",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": false
        },
        {
            "TimePeriod": {
                "Start": "2022-06-01",
                "End": "2022-06-30"
            },
            "Total": {},
            "Groups": [
                {
                    "Keys": [
                        "Amazon Simple Storage Service",
                        "Environment$"
                    ],
                    "Metrics": {
                        "BlendedCost": {
                            "Amount": "0.0007916097",
                            "Unit": "USD"
                        },
                        "UnblendedCost": {
                            "Amount": "0.0007916097",
                            "Unit": "USD"
                        },
                        "UsageQuantity": {
                            "Amount": "452.0000076759",
                            "Unit": "N/A"
                        }
                    }
                }
            ],
            "Estimated": true
        }
    ],
    "DimensionValueAttributes": []
}
```
