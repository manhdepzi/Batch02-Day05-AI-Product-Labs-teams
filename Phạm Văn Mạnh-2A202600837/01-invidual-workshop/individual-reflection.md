# Individual Reflection - Pham Van Manh - 2A202600837

## 1. Vai tro ca nhan

Trong Day 05, em phu trach phan dung thu va mo trai nghiem Moni trong MoMo. Em tap trung vao mot case cu the: user hoi ve kha nang dat muc tieu 200 trieu khi moi thang co the kiem/tiet kiem 12 trieu.

Vai tro chinh:

- Chon case test that trong app Moni.
- Ghi lai bang chung bang anh chup man hinh.
- Phan tich loi trong cau tra loi cua AI.
- Chuyen nhan xet UX thanh product decision co the dua vao SPEC.

## 2. Viec da lam

Em da thu prompt:

```text
Moi thang co the kiem duoc 12 trieu, den thang 1 nam sau muon duoc 200 trieu thi kha nang la bao nhieu phan tram?
```

Ket qua quan sat:

- Moni tinh 12 trieu x 8 thang = 96 trieu.
- Moni ket luan 96 trieu bang 48% cua muc tieu 200 trieu.
- Tuy nhien, user hoi "kha nang dat 200 trieu", khong hoi "da hoan thanh bao nhieu phan tram muc tieu".
- Voi du lieu hien tai, kha nang dat du 200 trieu la 0% neu khong doi thu nhap, thoi gian hoac muc tieu.

Em da tao file HTML `momo_moni_ux_workshop.html` de trinh bay phan danh gia UX kem 2 anh bang chung.

## 3. AI ho tro phan nao

AI duoc dung de:

- He thong hoa lai nhan xet thanh cac muc: evidence, pain point, failure mode, to-be flow.
- Goi y cach viet finding theo ngon ngu product.
- Chuyen loi "AI tra loi sai" thanh yeu cau san pham: can phan biet "ty le hoan thanh" va "kha nang dat muc tieu".
- Ho tro viet evidence pack va thin SPEC cho prototype Day 06.

AI khong thay the viec quan sat cua em. Bang chung chinh van den tu anh chup man hinh va viec em tu dung app.

## 4. Bai hoc sau demo / sau buoi lam

Bai hoc lon nhat la mot AI co the tinh dung nhung van tra loi sai neu hieu sai intent cua user. Trong case nay, phep tinh 96 trieu va 48% khong sai, nhung ket luan san pham sai vi no tra loi "tien do" thay vi "kha nang".

Khi build prototype AI Product, em can quan tam den:

- User that su dang can quyet dinh gi?
- AI dang augment hay automate phan nao?
- Neu AI khong chac intent, no co hoi lai khong?
- Neu AI tra loi sai, user co cach sua va quay lai quyet dinh dung khong?

## 5. Dieu se dua vao prototype Day 06

Prototype nen co mot flow tu van muc tieu tai chinh hep:

- Nhan dau vao ve muc tieu, thoi gian va dong tien hang thang.
- Tinh kha nang dat muc tieu theo gia dinh hien tai.
- Neu khong dat, noi ro "khong dat" thay vi chi dua phan tram tien do.
- Goi y 2-3 cach dieu chinh: tang so tien moi thang, keo dai thoi gian, hoac giam muc tieu.
- Neu cau hoi mo ho, AI phai hoi lai truoc khi ket luan.
