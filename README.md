// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
https://prod.liveshare.vsengsaas.visualstudio.com/join?6B168CABE3E0285BDB169ED828163CAE1AE6
using System;
using System.Collections.Generic;

namespace QuanLySinhVienApp
{
    // Bước 1: Tạo lớp SinhVien (Tính đóng gói)
    class SinhVien
    {
        // Các thuộc tính để private (phạm vi truy cập riêng tư)
        private string msv;
        private string hoTen;
        private int tuoi;

        // Constructor: Khởi tạo đối tượng có tham số (giống trong ảnh bạn gửi)
        public SinhVien(string msv, string hoTen, int tuoi)
        {
            this.msv = msv;
            this.hoTen = hoTen;
            this.tuoi = tuoi;
        }

        // Constructor không tham sốz
        public SinhVien() { }

        // Các hành vi (Phương thức)
        public void DisplaySV()
        {
            Console.WriteLine($"MSV: {msv} | Ho Ten: {hoTen} | Tuoi: {tuoi}");
        }

        // Getter và Setter để truy cập an toàn (Phòng trường hợp bạn cần dùng)
        public string GetMSV() { return msv; }
        public void SetHoTen(string ten Moi) { hoTen = tenMoi; }
    }

    class Program
    {
        static void Main(string[] args)
        {
            // Bước 2: Sử dụng mảng để quản lý (giống dòng 51 trong ảnh)
            Console.WriteLine("--- Chuong trinh Quan ly Sinh vien ---");

            SinhVien[] danhSach = new SinhVien[5];

            // Khởi tạo đối tượng bằng từ khóa 'new'
            danhSach[0] = new SinhVien("2305htta012", "Nguyen Van A", 19);
            danhSach[1] = new SinhVien("2305htta014", "Tran Thi B", 20);

            // Hiển thị thông tin
            Console.WriteLine("\nThong tin sinh vien 1:");
            danhSach[0].DisplaySV();

            Console.WriteLine("Thong tin sinh vien 2:");
            danhSach[1].DisplaySV();

            // Phần nhập thêm sinh viên từ bàn phím (Nếu bạn muốn mở rộng)
            Console.WriteLine("\nNhap thong tin cho sinh vien thu 3:");
            Console.Write("Nhap MSV: ");
            string ma = Console.ReadLine();
            Console.Write("Nhap Ho ten: ");
            string ten = Console.ReadLine();
            Console.Write("Nhap Tuoi: ");
            int t = int.Parse(Console.ReadLine());

            danhSach[2] = new SinhVien(ma, ten, t);

            Console.WriteLine("\nDanh sach sau khi cap nhat:");
            for (int i = 0; i < 3; i++)
            {
                danhSach[i].DisplaySV();
            }

            // Dừng màn hình để xem kết quả (Dành cho Visual Studio)
            Console.WriteLine("\nNhan phim bat ky de thoat...");
            Console.ReadKey();
        }
    }
}
