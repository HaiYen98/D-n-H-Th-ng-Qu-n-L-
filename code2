class TaiLieu:
    def __init__(self, maTaiLieu, nhaXuatBan, soBanPhatHanh):
        self.__maTaiLieu = maTaiLieu
        self.__nhaXuatBan = nhaXuatBan
        self.__soBanPhatHanh = soBanPhatHanh

    def getInfo(self):
        print(f"Ma tai lieu: {self.__maTaiLieu}")
        print(f"Nha xuat ban: {self.__nhaXuatBan}")
        print(f"So ban phat hanh: {self.__soBanPhatHanh}")

    def getMaTaiLieu(self):
        return self.__maTaiLieu


class Sach(TaiLieu):
    def __init__(self, maTaiLieu, nhaXuatBan, soBanPhatHanh, tenTacGia, soTrang):
        super().__init__(maTaiLieu, nhaXuatBan, soBanPhatHanh)
        self.__tenTacGia = tenTacGia
        self.__soTrang = soTrang

    def getInfo(self):
        print("The loai: Sach")
        super().getInfo()
        print(f"Ten tac gia: {self.__tenTacGia}")
        print(f"So trang: {self.__soTrang}")


class TapChi(TaiLieu):
    def __init__(self, maTaiLieu, nhaXuatBan, soBanPhatHanh, soPhatHanh, thangPhatHanh):
        super().__init__(maTaiLieu, nhaXuatBan, soBanPhatHanh)
        self.__soPhatHanh = soPhatHanh
        self.__thangPhatHanh = thangPhatHanh

    def getInfo(self):
        print("The loai: Tap chi")
        super().getInfo()
        print(f"So phat hanh: {self.__soPhatHanh}")
        print(f"Thang phat hanh: {self.__thangPhatHanh}")


class Bao(TaiLieu):
    def __init__(self, maTaiLieu, nhaXuatBan, soBanPhatHanh, ngayPhatHanh):
        super().__init__(maTaiLieu, nhaXuatBan, soBanPhatHanh)
        self.__ngayPhatHanh = ngayPhatHanh

    def getInfo(self):
        print("The loai: Bao")
        super().getInfo()
        print(f"Ngay phat hanh: {self.__ngayPhatHanh}")


class QuanLySach:
    def __init__(self):
        self.__danhSachTaiLieu = []

    def themTaiLieu(self, taiLieuThem):
        self.__danhSachTaiLieu.append(taiLieuThem)
        print("Them tai lieu thanh cong!")

    def xoaTaiLieu(self, maCanXoa):
        for taiLieu in self.__danhSachTaiLieu:
            if taiLieu.getMaTaiLieu() == maCanXoa:
                self.__danhSachTaiLieu.remove(taiLieu)
                print("Xoa tai lieu thanh cong!")
                return
        print("Khong tim thay tai lieu!")

    def hienThiTaiLieu(self):
        if not self.__danhSachTaiLieu:
            print("Danh sach trong!")
            return
        print("-" * 50)
        print("\nDANH SACH TAI LIEU")
        for taiLieu in self.__danhSachTaiLieu:
            taiLieu.getInfo()
            print("-" * 50)

    def timKiemTheLoai(self, theLoaiCanTim):
        found = False
        theLoaiCanTim = theLoaiCanTim.lower().strip()
        print(f"\nKet qua tim kiem theo the loai '{theLoaiCanTim}':")
        for taiLieu in self.__danhSachTaiLieu:
            if theLoaiCanTim == "sach" and isinstance(taiLieu, Sach):
                taiLieu.getInfo()
                print("-" * 50)
                found = True
            elif theLoaiCanTim == "tap chi" and isinstance(taiLieu, TapChi):
                taiLieu.getInfo()
                print("-" * 50)
                found = True
            elif theLoaiCanTim == "bao" and isinstance(taiLieu, Bao):
                taiLieu.getInfo()
                print("-" * 50)
                found = True
        if not found:
            print("Khong tim thay tai lieu!")


def nhapThongTin():
    quanLy = QuanLySach()
    while True:
        print("-" * 50)
        print("QUAN LY THU VIEN".center(50))
        print("-" * 50)
        print("1. Them tai lieu moi")
        print("2. Xoa tai lieu")
        print("3. Hien thi danh sach tai lieu")
        print("4. Tim kiem theo the loai")
        print("5. Thoat chuong trinh")
        print("-" * 50)
        try:
            choice = int(input("Nhap lua chon cua ban: "))
        except ValueError:
            print("Vui long nhap so nguyen hop le!")
            continue

        if choice == 1:
            print("-" * 50)
            print("Them tai lieu moi".center(50))
            print("-" * 50)
            print("1. Sach")
            print("2. Tap chi")
            print("3. Bao")
            print("-" * 50)
            try:
                loaiTaiLieu = int(input("Chon loai tai lieu: "))
                maTaiLieu = input("Nhap ma tai lieu: ").strip()
                if not maTaiLieu:
                    print("Ma tai lieu khong duoc de trong!")
                    continue
                nhaXuatBan = input("Nhap nha xuat ban: ").strip()
                if not nhaXuatBan:
                    print("Nha xuat ban khong duoc de trong!")
                    continue
                soBanPhatHanh = int(input("Nhap so ban phat hanh: "))
                if soBanPhatHanh <= 0:
                    print("So ban phat hanh phai lon hon 0!")
                    continue

                if loaiTaiLieu == 1:
                    tenTacGia = input("Nhap ten tac gia: ").strip()
                    if not tenTacGia:
                        print("Ten tac gia khong duoc de trong!")
                        continue
                    soTrang = int(input("Nhap so trang: "))
                    if soTrang <= 0:
                        print("So trang phai lon hon 0!")
                        continue
                    quanLy.themTaiLieu(Sach(maTaiLieu, nhaXuatBan, soBanPhatHanh, tenTacGia, soTrang))
                elif loaiTaiLieu == 2:
                    soPhatHanh = input("Nhap so phat hanh: ").strip()
                    if not soPhatHanh:
                        print("So phat hanh khong duoc de trong!")
                        continue
                    thangPhatHanh = input("Nhap thang phat hanh: ").strip()
                    if not thangPhatHanh:
                        print("Thang phat hanh khong duoc de trong!")
                        continue
                    quanLy.themTaiLieu(TapChi(maTaiLieu, nhaXuatBan, soBanPhatHanh, soPhatHanh, thangPhatHanh))
                elif loaiTaiLieu == 3:
                    ngayPhatHanh = input("Nhap ngay phat hanh: ").strip()
                    if not ngayPhatHanh:
                        print("Ngay phat hanh khong duoc de trong!")
                        continue
                    quanLy.themTaiLieu(Bao(maTaiLieu, nhaXuatBan, soBanPhatHanh, ngayPhatHanh))
                else:
                    print("Lua chon loai tai lieu khong hop le!")
            except ValueError:
                print("Vui long nhap so nguyen hop le cho cac truong so!")
        elif choice == 2:
            print("-" * 50)
            print("Xoa tai lieu".center(50))
            print("-" * 50)
            maCanXoa = input("Nhap ma tai lieu can xoa: ").strip()
            if not maCanXoa:
                print("Ma tai lieu khong duoc de trong!")
                continue
            quanLy.xoaTaiLieu(maCanXoa)
        elif choice == 3:
            print("-" * 50)
            quanLy.hienThiTaiLieu()
            print("-" * 50)
        elif choice == 4:
            print("-" * 50)
            print("Tim kiem theo the loai".center(50))
            print("-" * 50)
            theLoai = input("Nhap the loai can tim (sach/tap chi/bao): ").strip()
            if not theLoai:
                print("The loai khong duoc de trong!")
                continue
            quanLy.timKiemTheLoai(theLoai)
        elif choice == 5:
            print("Thoat chuong trinh!")
            break
        else:
            print("Lua chon khong hop le!")


# Chạy chương trình
if __name__ == "__main__":
    nhapThongTin()
