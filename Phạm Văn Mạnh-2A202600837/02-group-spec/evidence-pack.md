# Evidence Pack - Moni Goal Feasibility Slice

## 1. Nhom va track

**Ten nhom:** Moni Goal Planning  
**Track:** Finance / personal planning  
**Product/app da chon:** MoMo - Moni AI Assistant  
**Build slice dang nghi:** AI giup user kiem tra kha nang dat muc tieu tai chinh theo thoi gian va dong tien hang thang.

## 2. Self-use evidence

| Observation | Screenshot/link | Path lien quan | Dieu hoc duoc |
|---|---|---|---|
| User hoi kha nang dat 200 trieu khi moi thang co 12 trieu | `../01-invidual-workshop/z7895678691692_a3d8ab89c66c55ec5bda18cf701a0379.jpg` | Failure | Cau hoi can dap an ve kha nang dat muc tieu, khong chi tinh tien do |
| Moni tinh tong 96 trieu va dua con so 48% | `../01-invidual-workshop/z7895670178136_672030c79f83c03095b5c394c82073bf.jpg` | Failure | 48% la ty le hoan thanh muc tieu, khong phai kha nang dat 200 trieu |
| Moni khong hoi lai gia dinh thoi gian va y nghia "kiem duoc" | File HTML workshop | Low-confidence | Khi intent/gia dinh mo ho, AI nen hoi lai truoc khi ket luan |

## 3. User / review / social evidence

| Quote / review / observation | Nguon | User la ai? | Pain/failure mode |
|---|---|---|---|
| User hoi bang ngon ngu tu nhien ve muc tieu 200 trieu va thoi gian den thang 1 | Self-use trong app Moni | Nguoi dung ca nhan can lap ke hoach tien bac nhanh | AI hieu nham intent cau hoi |
| User can biet "co dat duoc khong" hon la "da duoc bao nhieu phan tram" | Suy ra tu task test | Nguoi dang ra quyet dinh tai chinh | Ket luan co the gay hieu nham |
| Can co nguon ngoai nhom ve viec user hay nham lan khi lap muc tieu tai chinh | Ke hoach lay nguon Day 06 | Nguoi moi lap ke hoach tai chinh | Neu chua kiem chung, scope phai giu hep |

Nguon ngoai nhom hien tai chua du manh. Day la gia dinh can kiem bang phong van nhanh 2-3 ban hoc hoac review/comment ve tro ly tai chinh truoc checkpoint M1 Day 06.

## 4. Competitor / analog evidence

| App / mo hinh tham khao | Ho xu ly task nay the nao? | Pattern hoc duoc | Co ap dung trong 1 ngay khong? |
|---|---|---|---|
| Calculator / spreadsheet | Tinh truc tiep so tien can co moi thang | Ket qua phai tach "dat/khong dat" va "can them bao nhieu" | Co |
| Budget planner | Cho user sua muc tieu, thoi gian, so tien hang thang | User can slider/input de tinh lai | Co |
| ChatGPT-style assistant | Hoi lai khi prompt mo ho | Low-confidence path nen hoi lai ngan gon | Co |

## 5. Evidence -> Insight

Evidence noi bat nhat:

Moni tinh dung phep tinh trong gia dinh cua no, nhung tra loi sai cau hoi chinh cua user. User hoi kha nang dat muc tieu, trong khi AI tra loi bang tien do hoan thanh.

Insight:

User khong chi can mot phep tinh phan tram. Ho can ho tro ra quyet dinh: "voi dieu kien hien tai toi co dat muc tieu khong, va neu khong thi phai doi bien so nao?"

Opportunity:

AI co the augment viec lap ke hoach bang cach tinh feasibility cua muc tieu, neu ro gia dinh, va dua 2-3 phuong an dieu chinh hep thay vi tra loi dai va mo ho.

## 6. Evidence doi SPEC nhu the nao?

- [x] Doi pain statement.
- [x] Doi build slice.
- [x] Doi Auto/Aug decision.
- [x] Doi 4 paths.
- [x] Doi failure mode.
- [x] Doi owner/test plan.

Truoc evidence, nhom co the build "tro ly tai chinh AI" kha rong. Sau evidence, nhom doi thanh mot slice hep: "AI kiem tra kha nang dat muc tieu tiet kiem va goi y dieu chinh". Ly do la loi nguy hiem nhat khong phai thieu tinh nang, ma la AI ket luan sai intent trong mot quyet dinh tai chinh.
