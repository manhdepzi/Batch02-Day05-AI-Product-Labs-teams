# App Teardown - Moni AI Assistant trong MoMo

## 1. Product da chon

**Product/app:** MoMo - Moni AI Assistant  
**AI feature:** Tro thu tai chinh, phan tich cau hoi va dua goi y tinh toan  
**User muc tieu:** Nguoi dung MoMo muon lap ke hoach tai chinh ca nhan nhanh bang ngon ngu tu nhien  
**Task test:** Hoi ve kha nang dat muc tieu 200 trieu khi moi thang co the kiem/tiet kiem 12 trieu

## 2. Promise vs reality

**Promise:** Moni co the dong vai tro tro thu tai chinh, giup user tinh toan va ra quyet dinh ve muc tieu tien bac.

**Ky vong:** Khi user hoi "kha nang dat 200 trieu la bao nhieu phan tram", AI can tra loi truc tiep ve kha nang dat muc tieu, neu khong dat thi noi ro khong dat.

**Reality:** Moni tinh ra 96 trieu va ket luan la 48% muc tieu. Cau tra loi co ve hop ly ve mat toan hoc, nhung sai intent vi 48% la ty le hoan thanh muc tieu, khong phai kha nang dat muc tieu.

## 3. Evidence

Bang chung nam trong cung folder:

- `z7895678691692_a3d8ab89c66c55ec5bda18cf701a0379.jpg`
- `z7895670178136_672030c79f83c03095b5c394c82073bf.jpg`
- `momo_moni_ux_workshop.html`

Observation chinh:

| Observation | Path lien quan | Dieu hoc duoc |
|---|---|---|
| User hoi ve "kha nang" dat 200 trieu | Failure | AI can phan biet intent xac suat/kha nang voi tien do muc tieu |
| Moni tinh 12 trieu x 8 thang = 96 trieu | Happy | AI lam dung mot phan phep tinh |
| Moni ket luan 48% | Failure | Ket luan dung cong thuc nhung sai cau hoi |
| Khong co buoc hoi lai ve thoi han, cach tinh, thang bat dau/ket thuc | Low-confidence | Khi gia dinh mo ho, AI nen hoi lai hoac neu ro gia dinh |

## 4. Four paths

| Path | As-is | To-be |
|---|---|---|
| Happy | Moni tinh duoc tong tien du kien | Moni noi ro co dat/khong dat, kem con so tien do |
| Low-confidence | Moni tu gia dinh 8 thang ma khong hoi lai | Moni hoi lai: tinh den dau thang 1 hay het thang 1, tien "kiem" hay "tiet kiem" |
| Failure | Moni tra loi 48% nhu dap an cho kha nang dat muc tieu | Moni noi "voi gia dinh hien tai khong dat, kha nang dat la 0% neu khong thay doi bien so" |
| Correction | User phai tu nhan ra 48% khong phai kha nang | User co the sua thoi gian/tien hang thang, AI tinh lai ngay |

## 5. Finding thanh product decision

Khi user hoi kha nang dat muc tieu tai chinh theo thoi gian, AI/product nham intent "kha nang dat" thanh "ty le hoan thanh muc tieu", hau qua la user co the hieu sai kha nang tai chinh cua minh. Loi thuoc layer Intent + UX Recovery. Nen sua bang low-confidence path: hoi lai gia dinh quan trong, tach rieng ket luan "dat/khong dat" voi "tien do bao nhieu phan tram", va cho user sua bien so de tinh lai.

## 6. As-is / To-be sketch

### As-is

```text
User hoi muc tieu 200tr
-> Moni tu hieu thoi gian la 8 thang
-> Moni tinh 12tr x 8 = 96tr
-> Moni chia 96/200 = 48%
-> User nhan dap an 48% va co the hieu nham day la kha nang dat muc tieu
```

### To-be

```text
User hoi muc tieu 200tr
-> AI tach intent: user muon biet co dat muc tieu hay khong
-> AI kiem tra gia dinh thoi gian va tien moi thang
-> Neu ro: tinh ket qua va ket luan "khong dat"
-> Neu mo ho: hoi lai 1-2 cau
-> AI dua 3 option dieu chinh: tang tien hang thang / keo dai thoi gian / giam muc tieu
-> User chon option, AI tinh lai
```

## 7. SPEC se doi gi

SPEC khong nen build chatbot tai chinh rong. Build slice nen chi la flow hep: "kiem tra kha nang dat mot muc tieu tiet kiem va goi y dieu chinh". Failure mode quan trong nhat la AI nham lan giua "tien do" va "kha nang dat".
