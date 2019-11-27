---
description: Istanbul Upgrade
---

# Upcoming HF 2019-12-12

* **Network:** xDai
* **Date:** 2019-12-12
* **Block Number:** TBD

## Description: Istanbul Upgrade

* eip1283ReenableTransition
* eip1344Transition
* eip1706Transition
* eip1884Transition
* eip2028Transition

## Perform Updates

1. **You must update spec.json and Parity node to version 2.6.5** as the spec format was changed.This requires a slightly different update process - _**Details Coming Soon**_.

## Verify

Once your update is complete, verify the HF block number:

```text
grep -n -A2 12095200 spec.json
```

You should see:

```text
46:    "eip1283ReenableTransition": 12095200,
47:    "eip1344Transition": 12095200,
48:    "eip1706Transition": 12095200,
49:    "eip1884Transition": 12095200,
50:    "eip2028Transition": 12095200
51-  },
52-  "genesis": {
--
98:          "12095200": {
99-            "info": "Istanbul HF",
100-            "price": {
--
120:          "12095200": {
121-            "info": "Istanbul HF",
122-            "price": {
--
143:          "12095200": {
144-            "info": "Istanbul HF",
145-            "price": {
--
159:          "12095200": {
160-            "info": "Istanbul HF",
161-            "price": {
```



