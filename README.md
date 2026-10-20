# Active Directory Lab (On-Premise, VMware Workstation Pro)

## Mục tiêu
Xây dựng hạ tầng Active Directory mô phỏng môi trường doanh nghiệp nhỏ,
thực hành quản trị AD DS, DNS, DHCP, GPO.
Quy mô công ty giả định

### Công ty: TechCorp Vietnam — 50 nhân sự, 6 phòng ban
| Phòng ban | Số lượng user | Viết tắt OU |
| --- | --- | --- |
| IT	| 5 | IT |
| HR (Nhân sự) | 5 | HR |
| Finance (Tài chính - Kế toán) | 8 | FIN |
| Sales (Kinh doanh) | 20 | SALES |
| Marketing | 7 | MKT |
| Management (Ban giám đốc) | 5 | MGMT |

### Quy ước đặt tên (Naming Convention) 
| Đối tượng | Format | Ví dụ |
| --- | --- | --- |
| Username	| `firstname.lastname` | `son.tran` |
| Email | `firstname.lastname@techcorp.local` | `son.tran@techcorp.local` |
| Máy tính | `TC-{DEPT}-{SỐ}` | `TC-SALES-001` |
| Security Group | `SG-{DEPT}-{Mục đích}` | `SG-SALES-FileAccess` |
| GPO | `GPO-{DEPT}-{Mục đích}` | `GPO-HR-USBBlock` |
### Security Group 
| Nhóm | Thành viên | Mục đích |
| --- | --- | --- |
| SG-IT-Admins	| 2 user IT | Toàn quyền quản trị domain |
| SG-IT-Helpdesk | 3 user IT | Chỉ reset password, không sửa GPO |
| SG-HR-FileAccess | 5 user HR | Truy cập share \DC01\HR |
| SG-FIN-FileAccess | 5 user HR | Truy cập share \DC01\HR |
| SG-SALES-FileAccess | 5 user HR | Truy cập share \DC01\HR |
| SG-MGMT-FullAccess | 5 user Management | Truy cập share \DC01\HR |
| SG-AllStaff-VPN | 50 user | Được phép kết nối WireGuard VPN |

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
