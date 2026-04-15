# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600396
**Name:** Duy Anh
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Cau tra loi hop ly vi du lieu da duoc lam sach, khong con record loi va khong bi outlier chi phoi. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent chon mot outlier cuc doan trong nhom electronics, dan den cau tra loi sai va phi thuc te. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trong bai nay hoat dong theo logic rat don gian: tim san pham co gia cao nhat trong nhom electronics. Khi du lieu la clean data, ket qua hop ly vi chi con cac ban ghi da duoc validation. Tuy nhien, garbage data chua nhieu loi chat luong nhu duplicate ID, kieu du lieu sai, gia tri null va dac biet la outlier gia rat lon. Record "Nuclear Reactor" co gia 999999 van nam trong category electronics nen agent xem day la lua chon tot nhat, du no khong phu hop voi bai toan mua sam thong thuong. Dieu nay cho thay agent khong that su "hieu" ngu canh, ma phu thuoc rat manh vao chat luong va cau truc cua data. Neu khong co buoc validation va quan sat du lieu, he thong co the dua ra ket luan sai nhung van nghe co ve tu tin va hop le.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Toi dong y. Prompt tot co the giup agent dien dat ro rang hon, nhung neu du lieu dau vao sai, thieu hoac bi nhiem rac thi cau tra loi van se sai. Trong bai lab nay, chi can thay doi chat luong data ma cung mot logic agent da dua ra hai ket qua rat khac nhau. Vi vay, quality data la nen tang quan trong hon de dam bao do tin cay cua he thong AI.
