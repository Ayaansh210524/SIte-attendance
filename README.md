# 🏢 HRMS - Enhanced Attendance System

A modern, feature-rich Human Resource Management System with geofence-based attendance tracking, employee management, and comprehensive reporting.

## ✨ Features

### Core Functionality
- **🔐 Secure Authentication** - Role-based access (Admin & Employee)
- **👥 Employee Management** - Add, verify, and manage employee records
- **📍 Geofence-Based Attendance** - Clock in/out only within office premises
- **📊 Attendance Reports** - 7-day history with detailed analytics
- **🆔 Document Verification** - Aadhar & PAN card verification
- **📱 QR Code Sharing** - Easy attendance link sharing

### Recent Enhancements (v2.0)
- ✅ **Dark Mode Toggle** - Theme switching for better UX
- ✅ **Session Management** - Auto-logout after 30 minutes of inactivity
- ✅ **Search & Filter** - Find employees by name, ID, or department
- ✅ **Data Export** - JSON, CSV export capabilities
- ✅ **Improved Validation** - Better error handling and user feedback
- ✅ **Responsive Design** - Mobile-friendly interface
- ✅ **Enhanced Security** - Try-catch blocks and error handling throughout
- ✅ **Duration Calculation** - Track working hours automatically

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Location services enabled
- No installation required!

### Quick Start

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Ayaansh210524/SIte-attendance.git
   cd SIte-attendance
   ```

2. **Open in Browser**
   ```bash
   # Simply open index.html in your browser
   # Or use a local server (recommended)
   python -m http.server 8000
   # Then visit http://localhost:8000
   ```

3. **Login with Demo Credentials**
   - **Admin Account**: `admin` / `admin123`
   - **Employee Account**: `emp001` / `123456`

## 🎯 Usage Guide

### For Admins

#### Employee Management
1. Navigate to **Admin Panel** tab
2. Click **➕ Add New Employee**
3. Fill in employee details:
   - Basic info (ID, Name, Department, DOB)
   - Contact details (Phone, Email, Address)
   - Upload photos (Employee photo, Aadhar, PAN)
   - Enter document numbers (Aadhar, PAN)
4. Click **✅ Add Employee**

#### Verification & Management
- **Verify**: Click "Verify" button to approve employee documents
- **Delete**: Remove employee records (careful: deletes all data)
- **Search**: Use search box to filter by name or ID
- **Filter**: Filter by department

#### Reports
- View 7-day attendance history
- See clock in/out times and working duration
- **📄 Export as PDF** - Generate PDF report
- **📊 Export as CSV** - Download CSV file

### For Employees

#### Attendance Clock In/Out
1. Navigate to **My Attendance** tab
2. Allow location access when prompted
3. Check geofence status (must be within 100m of office)
4. Click **✋ Clock In** to start work
5. Click **Clock Out** to end work
6. View today's working duration

#### View Profile
- See verified documents
- Check employee information
- Share attendance link via QR code

## 🔒 Security Features

- **LocalStorage Encryption Ready** - Can be enhanced with encryption
- **Session Timeout** - Auto-logout after 30 minutes of inactivity
- **Geofence Verification** - Prevents fake attendance
- **Document Verification** - Admin approval system
- **Password Hashing** - Ready for backend integration

## 🐛 Bug Fixes (v2.0)

| Issue | Status | Fix |
|-------|--------|-----|
| QR Code Script Placement | ✅ Fixed | Moved outside comment block, proper error handling |
| Missing Geo Status Styles | ✅ Fixed | Added `.geo-ok`, `.geo-fail`, `.checking` CSS classes |
| Attendance Status Styling | ✅ Fixed | Added `.status.present` and `.status.absent` classes |
| File Input Validation | ✅ Fixed | Improved validation logic for all file types |
| Error Handling | ✅ Fixed | Added try-catch blocks throughout |
| Dark Mode Support | ✅ Added | Toggle theme with persistent storage |
| Session Management | ✅ Added | 30-minute timeout with warning |
| Search Functionality | ✅ Added | Real-time search and filtering |
| CSV Export | ✅ Added | Download attendance reports |
| Duration Calculation | ✅ Added | Auto-calculate working hours |

## 📊 Data Structure

### Employee Record
```javascript
{
  id: "EMP001",
  name: "John Doe",
  department: "IT",
  dob: "1995-05-15",
  phone: "9876543210",
  email: "john@example.com",
  address: "123 Main Street",
  photo: "base64_image_data",
  aadhar: {
    number: "123456789012",
    image: "base64_image_data"
  },
  pan: {
    number: "ABCDE1234F",
    image: "base64_image_data"
  },
  createdAt: "2026-05-05T10:00:00Z",
  verified: true
}
```

### Attendance Record
```javascript
{
  empId: "EMP001",
  empName: "John Doe",
  type: "in",  // "in" or "out"
  timestamp: "2026-05-05T09:30:00Z",
  location: {
    lat: 28.6139,
    lng: 77.2090,
    accuracy: 50
  },
  distance: 45.23  // distance from office in meters
}
```

## ⚙️ Configuration

### Geofence Settings (in JavaScript)
```javascript
const OFFICE_LOCATION = { lat: 28.6139, lng: 77.2090 }; // Change to your office
const GEOFENCE_RADIUS = 100; // meters
const SESSION_TIMEOUT = 30 * 60 * 1000; // 30 minutes
```

### Update Office Location
1. Find your office latitude/longitude (use Google Maps)
2. Replace values in script section
3. Adjust GEOFENCE_RADIUS as needed

## 📱 API Endpoints (LocalStorage)

All data is stored in browser LocalStorage:
- `localStorage.getItem('users')` - User accounts
- `localStorage.getItem('employees')` - Employee records
- `localStorage.getItem('attendance')` - Attendance logs
- `localStorage.getItem('theme')` - User theme preference

## 🔧 Development

### Project Structure
```
SIte-attendance/
├── index.html          # Main application file
├── README.md          # This file
└── ROADMAP.md         # Development roadmap
```

### Technology Stack
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Storage**: Browser LocalStorage
- **Geolocation**: HTML5 Geolocation API
- **QR Code**: QRCode.js library

### Browser Compatibility
| Browser | Support |
|---------|---------|
| Chrome | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Edge | ✅ Full |
| IE 11 | ⚠️ Limited |

## 🚀 Future Enhancements

### Planned Features
- [ ] Backend integration (Node.js/Python)
- [ ] Database support (MongoDB/PostgreSQL)
- [ ] Email notifications
- [ ] SMS alerts
- [ ] PDF report generation
- [ ] Biometric verification
- [ ] Multi-location support
- [ ] Leave management
- [ ] Payroll integration
- [ ] Mobile app (React Native)

## 📋 Troubleshooting

### Issue: Location not detected
**Solution:**
- Check browser location permissions
- Enable GPS on your device
- Try in HTTPS (some browsers require it)
- Check if you're within range of office

### Issue: Can't clock in/out
**Solution:**
- Ensure you're within 100m of office
- Check geofence status indicator
- Verify location accuracy
- Try refreshing page

### Issue: Employee photos not showing
**Solution:**
- Check file size (max 5MB)
- Ensure supported format (JPEG, PNG, etc.)
- Try uploading again
- Clear browser cache

### Issue: Session timeout too soon
**Solution:**
- Modify `SESSION_TIMEOUT` in JavaScript
- Default is 30 minutes
- Adjust as needed for your organization

## 🔐 Security Considerations

### Current Implementation
✅ Client-side validation
✅ Session management
✅ Geofence verification
✅ Document verification

### Recommended Enhancements
- [ ] Backend authentication
- [ ] Database encryption
- [ ] HTTPS requirement
- [ ] Rate limiting
- [ ] Audit logs
- [ ] 2FA authentication

## 📝 License

This project is open source and available under the MIT License.

## 👤 Author

**Ayaansh Dubey**
- GitHub: [@Ayaansh210524](https://github.com/Ayaansh210524)
- Email: dubey.ayaansh21@gmail.com

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For issues, feature requests, or questions:
- Open a GitHub issue
- Check existing issues for solutions
- Review the ROADMAP.md for planned features

## 🎓 Learning Resources

- [HTML5 Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)
- [LocalStorage Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [QRCode.js Library](https://davidshimjs.github.io/qrcodejs/)
- [CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

---

**Version**: 2.0.0  
**Last Updated**: May 5, 2026  
**Status**: ✅ Production Ready
