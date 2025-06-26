# AWS Permissions

Voici les permissions spéciales qui ont été attribuées à votre équipe:\


### Pour le service "Billing"

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-portal:*Billing",
                "aws-portal:*Usage",
                "aws-portal:*PaymentMethods",
                "budgets:ViewBudget",
                "budgets:ModifyBudget",
                "ce:UpdatePreferences",
                "ce:CreateReport",
                "ce:UpdateReport",
                "ce:DeleteReport",
                "ce:CreateNotificationSubscription",
                "ce:UpdateNotificationSubscription",
                "ce:DeleteNotificationSubscription",
                "cur:DescribeReportDefinitions",
                "cur:PutReportDefinition",
                "cur:ModifyReportDefinition",
                "cur:DeleteReportDefinition",
                "purchase-orders:*PurchaseOrders"
            ],
            "Resource": "*"
        }
    ]
}
```

### Pour la gestion des budgets

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "budgets:DescribeBudgetActionsForAccount",
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Allow",
            "Action": "budgets:*",
            "Resource": "arn:aws:budgets::709024702237:budget/*"
        },
        {
            "Sid": "VisualEditor2",
            "Effect": "Allow",
            "Action": "budgets:*",
            "Resource": "arn:aws:budgets::709024702237:budget/*/action/*"
        }
    ]
}
```

### Pour le service de Cost Explorer

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "ce:UpdateNotificationSubscription",
                "ce:DeleteNotificationSubscription",
                "ce:DeleteReport",
                "ce:GetCostAndUsage",
                "ce:GetReservationPurchaseRecommendation",
                "ce:GetPreferences",
                "ce:GetReservationUtilization",
                "ce:UpdateReport",
                "ce:GetCostCategories",
                "ce:GetSavingsPlansPurchaseRecommendation",
                "ce:GetSavingsPlansUtilizationDetails",
                "ce:GetDimensionValues",
                "ce:UpdateCostAllocationTagsStatus",
                "ce:CreateCostCategoryDefinition",
                "ce:DescribeReport",
                "ce:GetReservationCoverage",
                "ce:CreateAnomalyMonitor",
                "ce:CreateReport",
                "ce:GetUsageForecast",
                "ce:DescribeNotificationSubscription",
                "ce:GetRightsizingRecommendation",
                "ce:CreateNotificationSubscription",
                "ce:GetSavingsPlansUtilization",
                "ce:CreateAnomalySubscription",
                "ce:ListCostCategoryDefinitions",
                "ce:GetCostForecast",
                "ce:GetCostAndUsageWithResources",
                "ce:ListCostAllocationTags",
                "ce:UpdatePreferences",
                "ce:ProvideAnomalyFeedback",
                "ce:GetSavingsPlansCoverage",
                "ce:GetTags"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Allow",
            "Action": "ce:*",
            "Resource": [
                "arn:aws:ce::709024702237:anomalymonitor/*",
                "arn:aws:ce::709024702237:anomalysubscription/*",
                "arn:aws:ce::709024702237:costcategory/*"
            ]
        }
    ]
}
```
