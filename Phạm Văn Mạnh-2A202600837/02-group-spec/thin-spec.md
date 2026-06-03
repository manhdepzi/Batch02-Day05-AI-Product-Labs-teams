# Thin SPEC - Moni Goal Feasibility Prototype

## 1. Track, product/app va user

**Track:** Finance / personal planning  
**Product/app that:** MoMo - Moni AI Assistant  
**User cu the:** Nguoi dung MoMo muon biet minh co dat muc tieu 200 trieu vao mot moc thoi gian cu the hay khong.  
**Nhom co phai user that khong?** Co mot phan. Nhom co the tu test nhu nguoi dung ca nhan, nhung can kiem chung them voi 2-3 user ben ngoai nhom trong Day 06.

## 2. Evidence summary

| Evidence | Nguon | User/pain noi len dieu gi? | SPEC phai doi gi? |
|---|---|---|---|
| Moni tra loi 48% cho cau hoi ve kha nang dat 200 trieu | Anh chup man hinh self-use | User co the hieu nham 48% la kha nang dat muc tieu | Tach "tien do" va "kha nang dat" |
| Moni tinh 96 trieu voi gia dinh 8 thang | Anh chup man hinh self-use | AI tu dat gia dinh ma khong hoi lai | Them low-confidence path hoi lai |
| User can biet can doi gi de dat muc tieu | Phan tich task | Output nen la quyet dinh va option hanh dong, khong chi la phep tinh | Them goi y tang tien/thoi gian/giam muc tieu |

## 3. Pain statement

```text
User dang gap kho o buoc danh gia kha nang dat muc tieu tai chinh,
vi AI nham lan giua "kha nang dat muc tieu" va "ty le hoan thanh muc tieu",
dan toi viec user co the hieu sai tinh kha thi cua ke hoach.
Bang chung chinh la anh chup man hinh Moni tra loi 48% cho case muc tieu 200 trieu trong khi tong tien du kien chi la 96 trieu.
```

## 4. Build slice

```text
Cho nguoi dung MoMo dang kiem tra muc tieu tiet kiem 200 trieu,
prototype se dung AI de augment viec tinh kha thi cua muc tieu,
tao ra ket luan dat/khong dat, tien do hien tai, so tien thieu va 2-3 option dieu chinh,
va xu ly failure mode nham lan "kha nang dat" voi "ty le hoan thanh" bang cach hoi lai gia dinh va tach ro hai loai ket qua.
```

## 5. Auto/Aug decision

- [x] **Augmentation:** AI goi y/tinh/draft, user quyet cuoi.
- [ ] **Conditional automation:** AI tu lam trong case hep; case mo ho/rui ro chuyen nguoi.
- [ ] **Automation:** AI tu quyet va tu hanh dong.

**Ly do chon:** Day la quyet dinh tai chinh ca nhan, nen AI khong nen tu dong chot hanh dong. AI chi nen tinh, giai thich gia dinh va dua option.  
**Human role:** decider / reviewer / rescuer.

## 6. Four paths

| Path | Prototype phai the hien gi? |
|---|---|
| Happy | User nhap muc tieu, thoi gian, tien moi thang; AI ket luan ro co dat hay khong va dua so tien thieu |
| Low-confidence | Neu thoi gian mo ho hoac "kiem duoc" khong ro la thu nhap hay tiet kiem, AI hoi lai 1-2 cau |
| Failure | AI khong duoc dung % tien do de tra loi nhu kha nang dat; prototype phai hien canh bao khi gap nham lan nay |
| Correction | User sua thoi gian/tien moi thang/muc tieu, AI tinh lai va cap nhat option |

## 7. Failure mode nguy hiem nhat

```text
Neu user hoi "kha nang dat muc tieu la bao nhieu phan tram",
AI co the tra loi bang ty le hoan thanh muc tieu thay vi ket luan kha thi,
hau qua la user hieu sai ve kha nang tai chinh cua minh.
Prototype se xu ly bang cach tach output thanh:
1. Ket luan dat/khong dat.
2. Tien do hien tai theo phan tram.
3. So tien thieu.
4. Option dieu chinh.
Owner kiem thu path nay la Pham Van Manh.
```

## 8. Owner plan cho sang Day 06

| Thanh vien | Viec phu trach | Bang chung can co trong repo |
|---|---|---|
| Pham Van Manh | Research / evidence | Anh chup man hinh Moni va app teardown |
| Pham Van Manh | SPEC | `thin-spec.md`, `evidence-pack.md` |
| Pham Van Manh | Prototype | Flow nhap muc tieu, thoi gian, tien moi thang |
| Pham Van Manh | Test / failure path | Test case 12 trieu/thang, muc tieu 200 trieu |
| Pham Van Manh | Demo script / repo | README va video/screenshot demo neu co |

## 9. Backlog khong build trong Day 06

- Luu lich su muc tieu dai han.
- Ket noi giao dich MoMo that.
- Tu dong tao ke hoach tiet kiem nhieu thang.
- Tu dong chuyen tien hoac dau tu.
