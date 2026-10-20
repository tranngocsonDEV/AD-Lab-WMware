# Active Directory Lab (On-Premise, VMware Workstation Pro)

## Mục tiêu
Xây dựng hạ tầng Active Directory mô phỏng môi trường doanh nghiệp nhỏ,
thực hành quản trị AD DS, DNS, DHCP, GPO.

## Công nghệ sử dụng
- VMware Workstation Pro
- Windows Server 2022 (Domain Controller)
- Windows 11 (Client)

## Sơ đồ kiến trúc
```directory
techcorp.local
├── OU=Departments
│   ├── OU=IT
│   │   ├── OU=Users
│   │   └── OU=Computers
│   ├── OU=HR
│   ├── OU=Finance
│   ├── OU=Sales
│   ├── OU=Marketing
│   └── OU=Management
├── OU=Service Accounts
├── OU=Admin Accounts       (tách riêng tài khoản admin, không để chung OU user thường)
└── OU=Disabled Users        (user nghỉ việc, không xóa ngay — đúng thực tế doanh nghiệp)
```
## Tiến độ
- [x] Cài Windows Server, promote Domain Controller
- [x] Cấu hình DNS, DHCP
- [x] Tạo OU, user, security group
- [ ] Cấu hình GPO (password policy, map drive, chặn USB)
- [ ] Join client vào domain
- [ ] File Server + phân quyền NTFS/Share
- [ ] Backup và test restore

## Vấn đề gặp phải
<!-- Ghi lại mỗi khi gặp lỗi và cách xử lý -->
<p align="center">
  <img src="./images/network_configuration.png" width="500">
</p>
<img>![alt text](image-1.png)</img>
## Hướng phát triển tiếp theo
- Đồng bộ lên Microsoft Entra ID (Entra Connect)
- Microsoft 365: user, license, MFA, Conditional Access
- Azure VM + NSG + RBAC
