Support costs for a full month used to be added to the billing exports in one billing line sometime after the month has finished. In the import_dist_lines step, we would get the support costs from the staging table (if already available) based on the 'OCBPremiumSupport' lineitem productcode, convert to the daily support cost (simply divide by. number of days in month), and distribute those costs over all aws billing lines based on the relative cost of that billingline. This happened in `_calculate_sup` query.

#changes 2023-10 A change has taken place in the way that AWS exports the support cost. Instead of not showing any support cost until the end of the month, now there is a billing line for support cost from the beginning of the month, and it is updated daily with the total amount until that day. Also there is a new lineitem productcode, namely 'AWSSupportEnterprise'. Furthermore the new support cost billing line now has the lineitemtype Usage instead of Fee. Because of this it is not filtered out when the mergedlines are imported from staging. Import_merged_lines `_insert_merged_lines.sql

```
WHERE (s.data -> 'lineitem' ->> 'lineitemtype' NOT IN ('Tax', 'Fee', 'RIFee', 'Refund', 'Credit', 'SavingsPlanRecurringFee', 'SavingsPlanUpfrontFee', 'SavingsPlanNegation','EdpDiscount'))
```


In [[V4|BDB4]] we wanted to estimate support cost during the month because we used to only get the support costs at the end of the month. However, with the change above that is no longer necessary.