# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600032
**Name:** Dao Vu Son
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Hop ly vi Laptop la san pham electronics co gia cao nhat trong du lieu sach. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Sai ve nghiep vu: outlier gia qua lon lam agent uu tien mot record phi thuc te. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung garbage data, agent bi dan dat boi cac loi chat luong du lieu. Dau tien, duplicate ID lam mat tinh nhat quan, co the khien he thong coi nham record la cung mot doi tuong. Thu hai, wrong data type nhu gia "ten dollars" lam pipeline tinh toan khong on dinh, co nguy co loi hoac bo sot record. Thu ba, outlier "Nuclear Reactor" gia 999999 ap dao logic chon gia cao nhat, nen agent tra loi phi thuc te. Cuoi cung, null values (id/category/price rong) lam giam do tin cay va bo canh ngu nghia. Ket qua la model co prompt tot van dua ra cau tra loi sai vi nguon tri thuc dau vao bi nhiem ban.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt tot chi giup dat cau hoi ro hon, nhung neu du lieu dau vao ban thi agent van suy luan tren thong tin sai. Trong thi nghiem nay, du lieu sach cho cau tra loi hop ly, con du lieu rac tao ra ket qua sai lech ro ret.
