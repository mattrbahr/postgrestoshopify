---
title: "Return Rates"
date: 2018-03-12T08:48:34-04:00
draft: false
showthedate: false
---

## This post is an overview of return rates.

I figured it out.

Extracting your return rate in Shopify requires you to 


```
SELECT
  returnst.Monthly,
  revt.total_rev::money,
  returnst.total_returns::money,
  ROUND(returnst.total_returns / revt.total_rev, 2) AS Return_rate
FROM
  (
   SELECT to_char(created_at, 'YYYY-MM') as Monthly,
   COUNT(amount) AS total_returns 
   FROM flagpolenyc_shopify.order_refunds__transactions
   GROUP BY to_char(created_at, 'YYYY-MM')
   ) returnst
   LEFT OUTER JOIN
   (
   SELECT to_char(created_at, 'YYYY-MM') as Monthly,
   COunT(subtotal_price) AS total_rev
   FROM flagpolenyc_shopify.orders
   GROUP BY to_char(created_at, 'YYYY-MM') 
   ) revt
  ON returnst.monthly = revt.monthly
 ORDER BY Monthly DESC
 ```