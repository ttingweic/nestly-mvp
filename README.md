# nestly-mvp
## 0.2.1

- 尿液顏色可選填；舊紀錄保留「未記錄」。
- 每餐一筆紀錄，可新增或移除食材，先名稱再重量（g）。
- 沿用 `nestly_records_v02` / `nestly_profile_v02`；不在載入時重寫舊資料。
- 舊食物的 `foodName` / `amount` 以單一食材編輯。新紀錄使用 `ingredients`，並保留名稱摘要和總重量供舊格式讀取。

## Regression test

With Node.js, Playwright and Google Chrome installed:

```sh
node records.test.cjs
# Test the deployed site in a fresh, isolated browser context:
NESTLY_URL=https://ttingweic.github.io/nestly-mvp/ node records.test.cjs
```

The test covers legacy data, multi-ingredient meals, urine color, edits, deletion, reload persistence and milk totals. Test data only goes into the isolated browser's local storage.

## 0.2.2

睡眠只保留日期、開始時間、結束時間及備註。開始睡眠後顯示「睡眠中」，補上結束時間可結束睡眠並顯示時長。結束時間早於開始時間時視為隔日；其他紀錄表單維持原樣。沿用舊儲存格式，舊睡眠以 startTime 或 time 作為開始時間，載入時不改寫資料。
