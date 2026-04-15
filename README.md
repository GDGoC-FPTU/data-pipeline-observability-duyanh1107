[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574007&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** anh.nguyenduy.work@gmail.com
**Name:** Duy Anh (duyanh1107)

---

## Mo ta

Day 10 lab nay tap trung vao xay dung mot ETL pipeline don gian va quan sat tac dong cua chat luong du lieu den ket qua cua agent. Trong bai lam nay, pipeline doc du lieu tu file JSON, loai bo cac record khong hop le, chuan hoa truong `category`, tinh them `discounted_price`, gan timestamp xu ly va luu ket qua ra file CSV.

Ngoai phan ETL, bai lab con mo phong mot agent tra loi dua tren du lieu clean va garbage data. Muc tieu la cho thay rang neu data dau vao khong duoc kiem soat chat luong, agent co the dua ra cau tra loi sai hoac gay hieu nham du prompt rat don gian.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

Lenh tren se tao file `processed_data.csv` tu file `raw_data.json`.

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

Quy trinh stress test:
1. Chay `python solution.py` de tao bo du lieu sach `processed_data.csv`.
2. Chay `python generate_garbage.py` de tao bo du lieu rac `garbage_data.csv`.
3. Chay `python agent_simulation.py` de so sanh cau tra loi cua agent tren hai bo du lieu.

---

## Cau truc thu muc

```text
├── solution.py              # ETL pipeline script
├── raw_data.json            # Nguon du lieu goc
├── processed_data.csv       # Output sau khi lam sach va transform
├── generate_garbage.py      # Tao du lieu rac de stress test
├── agent_simulation.py      # Mo phong agent tra loi dua tren data
├── experiment_report.md     # Bao cao ket qua thi nghiem
└── README.md                # Tai lieu tong quan
```

---

## Ket qua

Tu `raw_data.json`, pipeline doc tong cong 5 records. Sau buoc validation, 2 records bi loai bo do khong dat yeu cau: mot record co `price <= 0` va mot record co `category` rong. Con lai 3 records hop le duoc dua vao buoc transform.

Sau buoc transform, moi record co them cot `discounted_price` voi cong thuc `price * 0.9`, cot `category` duoc chuan hoa sang Title Case, va cot `processed_at` de ghi nhan thoi diem xu ly. Ket qua cuoi cung duoc luu vao `processed_data.csv`.

Thi nghiem voi agent cho thay bo du lieu clean giup agent dua ra cau tra loi hop ly hon, trong khi garbage data co the dan den viec agent chon mot san pham outlier phi thuc te. Dieu nay nhan manh vai tro cua data validation va observability trong cac he thong AI pipeline.
