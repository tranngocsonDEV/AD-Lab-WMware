# Active Directory Lab (On-Premise, VMware Workstation Pro)

## Mục tiêu
Xây dựng hạ tầng Active Directory mô phỏng môi trường doanh nghiệp nhỏ,
thực hành quản trị AD DS, DNS, DHCP, GPO.

## Công nghệ sử dụng
- VMware Workstation Pro
- Windows Server 2022 (Domain Controller)
- Windows 11 (Client)

## Sơ đồ kiến trúc
<!-- Chèn ảnh architecture-diagram.png khi vẽ xong -->

## Tiến độ
- [ ] Cài Windows Server, promote Domain Controller
- [ ] Cấu hình DNS, DHCP
- [ ] Tạo OU, user, security group
- [ ] Cấu hình GPO (password policy, map drive, chặn USB)
- [ ] Join client vào domain
- [ ] File Server + phân quyền NTFS/Share
- [ ] Backup và test restore

## Vấn đề gặp phải
<!-- Ghi lại mỗi khi gặp lỗi và cách xử lý -->

## Hướng phát triển tiếp theo
- Đồng bộ lên Microsoft Entra ID (Entra Connect)
- Microsoft 365: user, license, MFA, Conditional Access
- Azure VM + NSG + RBAC