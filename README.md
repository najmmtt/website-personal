# website-personal
web
[web1.html](https://github.com/user-attachments/files/25142747/web1.html)
<!DOCTYPE html>
<html lang="id">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SIAKAD SMKN 1 LA - VERSION V7 ULTIMATE</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap"
        rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="https://unpkg.com/html5-qrcode" type="text/javascript"></script>

    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4895ef;
            --dark: #0f172a;
            --light: #f8f9fa;
            --glass: rgba(255, 255, 255, 0.9);
            --sidebar-width: 280px;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f3f4f6;
            overflow-x: hidden;
            color: #333;
        }

        /* UTILITAS */
        .hidden {
            display: none !important;
        }

        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ================= LOGIN PAGE ================= */
        .login-wrapper {
            min-height: 100vh;
            background: linear-gradient(135deg, var(--dark) 0%, #1e293b 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            position: relative;
            overflow: hidden;
        }

        /* Background Shapes Animation */
        .shape {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            animation: float 10s infinite;
        }

        .shape:nth-child(1) {
            width: 200px;
            height: 200px;
            top: 10%;
            left: 10%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            width: 300px;
            height: 300px;
            bottom: 10%;
            right: 10%;
            animation-delay: 2s;
        }

        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
            }

            50% {
                transform: translateY(-20px) rotate(10deg);
            }

            100% {
                transform: translateY(0) rotate(0deg);
            }
        }

        .login-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 40px;
            width: 100%;
            max-width: 450px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.3);
            z-index: 10;
        }

        .login-header i {
            background: var(--primary);
            color: white;
            width: 80px;
            height: 80px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            margin-bottom: 20px;
            box-shadow: 0 10px 20px rgba(67, 97, 238, 0.3);
        }

        /* ================= DASHBOARD LAYOUT ================= */
        .sidebar {
            width: var(--sidebar-width);
            height: 100vh;
            position: fixed;
            top: 0;
            left: 0;
            background: var(--dark);
            color: white;
            padding: 25px;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 5px 0 15px rgba(0, 0, 0, 0.1);
        }

        .brand {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 40px;
            display: flex;
            align-items: center;
            gap: 10px;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .menu-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: #64748b;
            margin-bottom: 15px;
            margin-top: 25px;
            font-weight: 600;
        }

        .nav-link-custom {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            color: #94a3b8;
            text-decoration: none;
            border-radius: 12px;
            margin-bottom: 8px;
            transition: all 0.3s;
            cursor: pointer;
            border: none;
            background: transparent;
            width: 100%;
            text-align: left;
            font-family: inherit;
            font-size: 0.95rem;
        }

        .nav-link-custom:hover,
        .nav-link-custom.active {
            background: var(--primary);
            color: white;
            box-shadow: 0 4px 12px rgba(67, 97, 238, 0.4);
            transform: translateX(5px);
        }

        .nav-link-custom i {
            width: 25px;
            font-size: 1.1rem;
        }

        .main-content {
            margin-left: var(--sidebar-width);
            padding: 30px;
            min-height: 100vh;
        }

        /* ================= COMPONENTS ================= */
        .topbar {
            background: white;
            padding: 15px 30px;
            border-radius: 15px;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.03);
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .user-profile-pill {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 5px;
            padding-right: 20px;
            background: #f8fafc;
            border-radius: 50px;
            border: 1px solid #e2e8f0;
        }

        .user-avatar-top {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* CARD STYLES */
        .card-glass {
            background: white;
            border: none;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            margin-bottom: 25px;
            transition: transform 0.3s;
        }

        .card-glass:hover {
            transform: translateY(-5px);
        }

        .card-header-custom {
            padding: 20px 25px;
            background: white;
            border-bottom: 1px solid #f1f5f9;
            font-weight: 600;
            font-size: 1.1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* PROFILE SPECIFIC */
        .profile-cover {
            height: 180px;
            background: linear-gradient(45deg, var(--primary), #4cc9f0);
            position: relative;
        }

        .profile-img-container {
            position: absolute;
            bottom: -60px;
            left: 40px;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: white;
            padding: 5px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .profile-img-main {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #f8fafc;
        }

        .btn-edit-foto {
            position: absolute;
            bottom: 5px;
            right: 5px;
            background: var(--dark);
            color: white;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: 0.2s;
        }

        .btn-edit-foto:hover {
            transform: scale(1.1);
        }

        .profile-info {
            padding: 80px 40px 40px 40px;
        }

        /* QR SCANNER */
        #reader {
            width: 100%;
            border-radius: 15px;
            overflow: hidden;
            border: 5px solid var(--dark);
        }

        /* TABLES */
        .table-custom {
            width: 100%;
            border-collapse: separate;
            border-spacing: 0 10px;
        }

        .table-custom thead th {
            border: none;
            padding: 15px;
            background: #f1f5f9;
            color: #64748b;
            font-weight: 600;
            font-size: 0.85rem;
            text-transform: uppercase;
        }

        .table-custom tbody tr {
            background: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.02);
            transition: 0.2s;
        }

        .table-custom tbody tr:hover {
            transform: scale(1.01);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .table-custom td {
            padding: 15px;
            border: none;
            vertical-align: middle;
        }

        .table-custom td:first-child {
            border-radius: 10px 0 0 10px;
        }

        .table-custom td:last-child {
            border-radius: 0 10px 10px 0;
        }

        /* RESPONSIVE */
        @media (max-width: 991px) {
            .sidebar {
                transform: translateX(-100%);
            }

            .main-content {
                margin-left: 0;
            }

            .sidebar.show {
                transform: translateX(0);
            }
        }
    </style>
</head>

<body>

    <div id="view-login" class="login-wrapper">
        <div class="shape"></div>
        <div class="shape"></div>

        <div class="login-card text-center fade-in">
            <div class="login-header">
                <i class="fas fa-university fa-3x"></i>
                <h3 class="fw-bold text-dark">SIAKAD SMKN 1</h3>
                <p class="text-muted small">Sistem Informasi Akademik & Presensi V.7.0</p>
            </div>

            <div class="text-start mt-4">
                <div class="mb-3">
                    <label class="form-label fw-bold small text-uppercase text-secondary">Login Sebagai</label>
                    <div class="input-group">
                        <span class="input-group-text bg-light border-0"><i
                                class="fas fa-user-shield text-primary"></i></span>
                        <select id="role-select" class="form-select border-0 bg-light py-2"
                            onchange="toggleLoginInput()">
                            <option value="">-- Pilih Akses --</option>
                            <option value="guru">Guru / Pengajar</option>
                            <option value="siswa">Siswa / Murid</option>
                            <option value="petugas">Petugas Piket / Satpam</option>
                            <option value="admin">Administrator</option>
                        </select>
                    </div>
                </div>

                <div id="guru-input-group" class="hidden fade-in mb-3">
                    <label class="form-label fw-bold small text-uppercase text-secondary">Nama Guru</label>
                    <select id="guru-name" class="form-select bg-light border-0"></select>
                </div>

                <div id="siswa-input-group" class="hidden fade-in mb-3">
                    <label class="form-label fw-bold small text-uppercase text-secondary">Nama Siswa</label>
                    <select id="siswa-name" class="form-select bg-light border-0"></select>
                </div>

                <div class="d-grid mt-4">
                    <button onclick="login()" class="btn btn-primary btn-lg fw-bold rounded-pill shadow-sm">
                        MASUK APLIKASI <i class="fas fa-arrow-right ms-2"></i>
                    </button>
                </div>
            </div>

            <div class="mt-4 text-muted small">
                &copy; 2026 Tim IT SMKN 1 Lemahabang
            </div>
        </div>
    </div>

    <div id="view-dashboard" class="hidden">

        <nav class="sidebar">
            <div class="brand">
                <i class="fas fa-cube text-primary"></i>
                <span>SMK BISA</span>
            </div>

            <div id="menu-guru" class="menu-group hidden">
                <div class="menu-label">Akademik</div>
                <button class="nav-link-custom active" onclick="nav('guru-home')"><i class="fas fa-home"></i>
                    Dashboard</button>
                <button class="nav-link-custom" onclick="nav('guru-nilai')"><i class="fas fa-pen-fancy"></i> Input
                    Nilai</button>
                <button class="nav-link-custom" onclick="nav('guru-jurnal')"><i class="fas fa-book"></i> Jurnal
                    Mengajar</button>
            </div>

            <div id="menu-siswa" class="menu-group hidden">
                <div class="menu-label">Data Saya</div>
                <button class="nav-link-custom active" onclick="nav('siswa-home')"><i class="fas fa-id-card"></i> Profil
                    Lengkap</button>
                <button class="nav-link-custom" onclick="nav('siswa-jadwal')"><i class="fas fa-calendar-alt"></i> Jadwal
                    Pelajaran</button>
                <button class="nav-link-custom" onclick="nav('siswa-nilai')"><i class="fas fa-chart-bar"></i> Kartu
                    Hasil Studi</button>
            </div>

            <div id="menu-petugas" class="menu-group hidden">
                <div class="menu-label">Presensi</div>
                <button class="nav-link-custom active" onclick="nav('petugas-scan')"><i class="fas fa-qrcode"></i> Scan
                    Kehadiran</button>
                <button class="nav-link-custom" onclick="nav('petugas-log')"><i class="fas fa-history"></i> Log
                    Harian</button>
            </div>

            <div id="menu-admin" class="menu-group hidden">
                <div class="menu-label">Master Data</div>
                <button class="nav-link-custom active" onclick="nav('admin-home')"><i class="fas fa-cogs"></i>
                    Pengaturan</button>
            </div>

            <div style="position: absolute; bottom: 30px; left: 25px; width: calc(100% - 50px);">
                <button onclick="logout()" class="btn btn-outline-danger w-100 rounded-pill"><i
                        class="fas fa-sign-out-alt me-2"></i> Log Out</button>
            </div>
        </nav>

        <main class="main-content">

            <div class="topbar fade-in">
                <div>
                    <h4 class="fw-bold mb-0 text-dark" id="page-title">Dashboard</h4>
                    <small class="text-muted" id="current-date">Senin, 1 Januari 2026</small>
                </div>
                <div class="user-profile-pill">
                    <div class="text-end d-none d-md-block">
                        <div class="fw-bold text-dark small" id="user-name-display">User Name</div>
                        <div class="text-muted" style="font-size: 0.75rem;" id="user-role-display">Role</div>
                    </div>
                    <img src="" id="topbar-img" class="user-avatar-top" alt="Profile">
                </div>
            </div>

            <div id="page-siswa-home" class="page-section hidden fade-in">
                <div class="row">
                    <div class="col-lg-8">
                        <div class="card-glass">
                            <div class="profile-cover">
                                <div class="position-absolute top-0 end-0 p-3 text-white">
                                    <span class="badge bg-white text-primary rounded-pill px-3">Active Student</span>
                                </div>
                            </div>
                            <div class="profile-img-container">
                                <img src="" id="disp-foto" class="profile-img-main">
                                <button class="btn-edit-foto" onclick="openEditProfile()" title="Ganti Foto">
                                    <i class="fas fa-camera"></i>
                                </button>
                            </div>
                            <div class="profile-info">
                                <div class="d-flex justify-content-between align-items-start">
                                    <div>
                                        <h2 class="fw-bold text-dark mb-1" id="disp-nama">Nama Siswa</h2>
                                        <p class="text-muted mb-3"><i class="fas fa-graduation-cap me-2"></i>Kelas XI
                                            TKJ 2</p>
                                    </div>
                                    <button onclick="openEditProfile()"
                                        class="btn btn-primary rounded-pill px-4 shadow-sm">
                                        <i class="fas fa-edit me-2"></i> Edit Data
                                    </button>
                                </div>

                                <div class="p-3 bg-light rounded-3 mb-4 mt-3 border">
                                    <h6 class="fw-bold text-secondary mb-2">Tentang Saya (Bio):</h6>
                                    <p class="mb-0 text-dark fst-italic" id="disp-bio">Belum ada deskripsi...</p>
                                </div>

                                <h5 class="fw-bold border-bottom pb-2 mb-3">Informasi Detail</h5>
                                <div class="row g-4">
                                    <div class="col-md-6">
                                        <div class="d-flex align-items-center">
                                            <div class="bg-blue-100 p-2 rounded me-3 text-primary"><i
                                                    class="fas fa-star"></i></div>
                                            <div><small class="text-muted d-block">Hobi</small><span class="fw-bold"
                                                    id="disp-hobi">-</span></div>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <div class="d-flex align-items-center">
                                            <div class="bg-blue-100 p-2 rounded me-3 text-primary"><i
                                                    class="fas fa-rocket"></i></div>
                                            <div><small class="text-muted d-block">Cita-Cita</small><span
                                                    class="fw-bold" id="disp-cita">-</span></div>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <div class="d-flex align-items-center">
                                            <div class="bg-blue-100 p-2 rounded me-3 text-primary"><i
                                                    class="fas fa-envelope"></i></div>
                                            <div><small class="text-muted d-block">Email</small><span class="fw-bold"
                                                    id="disp-email">-</span></div>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <div class="d-flex align-items-center">
                                            <div class="bg-blue-100 p-2 rounded me-3 text-primary"><i
                                                    class="fas fa-phone"></i></div>
                                            <div><small class="text-muted d-block">WhatsApp</small><span class="fw-bold"
                                                    id="disp-hp">-</span></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-lg-4">
                        <div class="card-glass p-4 text-center">
                            <h6 class="fw-bold mb-3 text-uppercase letter-spacing-1">ID Card Digital</h6>
                            <div class="bg-white p-3 d-inline-block rounded border shadow-sm mb-3">
                                <div id="my-qr-code"></div>
                            </div>
                            <p class="small text-muted mb-0">Tunjukkan QR Code ini kepada petugas piket untuk melakukan
                                absensi kehadiran.</p>
                        </div>

                        <div class="card-glass p-4">
                            <h6 class="fw-bold mb-3">Statistik Kehadiran</h6>
                            <div class="d-flex justify-content-between mb-2"><small>Hadir</small> <span
                                    class="fw-bold text-success">95%</span></div>
                            <div class="progress mb-3" style="height: 6px;">
                                <div class="progress-bar bg-success" style="width: 95%"></div>
                            </div>

                            <div class="d-flex justify-content-between mb-2"><small>Izin</small> <span
                                    class="fw-bold text-warning">2%</span></div>
                            <div class="progress mb-3" style="height: 6px;">
                                <div class="progress-bar bg-warning" style="width: 2%"></div>
                            </div>

                            <div class="d-flex justify-content-between mb-2"><small>Sakit</small> <span
                                    class="fw-bold text-info">3%</span></div>
                            <div class="progress" style="height: 6px;">
                                <div class="progress-bar bg-info" style="width: 3%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="page-siswa-jadwal" class="page-section hidden fade-in">
                <div class="card-glass">
                    <div class="card-header-custom">
                        <span><i class="fas fa-calendar-week me-2 text-primary"></i> Jadwal Pelajaran</span>
                        <button class="btn btn-sm btn-outline-primary">Download PDF</button>
                    </div>
                    <div class="p-4">
                        <table class="table-custom text-center">
                            <thead>
                                <tr>
                                    <th>Hari</th>
                                    <th>Jam Ke-</th>
                                    <th>Mata Pelajaran</th>
                                    <th>Guru Pengampu</th>
                                    <th>Status</th>
                                </tr>
                            </thead>
                            <tbody id="tbody-jadwal-siswa">
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <div id="page-siswa-nilai" class="page-section hidden fade-in">
                <div class="row" id="container-nilai-siswa">
                </div>
            </div>

            <div id="page-guru-home" class="page-section hidden fade-in">
                <div class="row g-4 mb-4">
                    <div class="col-md-4">
                        <div class="card-glass p-4 bg-primary text-white">
                            <h3>36 Siswa</h3>
                            <small>Total Siswa Diampu</small>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="card-glass p-4 bg-success text-white">
                            <h3>12 Mapel</h3>
                            <small>Jam Mengajar Minggu Ini</small>
                        </div>
                    </div>
                </div>
                <div class="card-glass p-4">
                    <h5 class="fw-bold">Selamat Datang di Panel Guru</h5>
                    <p>Silakan pilih menu di samping untuk input nilai atau mengisi jurnal mengajar.</p>
                </div>
            </div>

            <div id="page-guru-nilai" class="page-section hidden fade-in">
                <div class="card-glass">
                    <div class="card-header-custom">
                        <span>Input Nilai Siswa</span>
                        <select class="form-select w-auto form-select-sm">
                            <option>Kelas 11 TKJ</option>
                        </select>
                    </div>
                    <div class="p-3">
                        <div class="table-responsive">
                            <table class="table table-hover align-middle">
                                <thead class="table-light">
                                    <tr>
                                        <th>Nama Siswa</th>
                                        <th>Tugas 1</th>
                                        <th>Tugas 2</th>
                                        <th>UTS</th>
                                        <th>UAS</th>
                                        <th>Aksi</th>
                                    </tr>
                                </thead>
                                <tbody id="tbody-input-nilai"></tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <div id="page-petugas-scan" class="page-section hidden fade-in">
                <div class="row justify-content-center">
                    <div class="col-md-6">
                        <div class="card-glass text-center p-4">
                            <div class="mb-3">
                                <span class="badge bg-danger animate-pulse">LIVE CAMERA</span>
                            </div>
                            <h4 class="fw-bold mb-3">SCANNER KEHADIRAN</h4>
                            <div id="reader"></div>
                            <p class="text-muted mt-3">Arahkan kamera ke QR Code Siswa. Pastikan cahaya cukup.</p>
                            <div id="scan-result" class="mt-3 fw-bold text-success"></div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="page-admin-home" class="page-section hidden fade-in">
                <div class="alert alert-warning border-0 shadow-sm text-dark">
                    <i class="fas fa-lock me-2"></i> Halaman Administrator. Gunakan dengan bijak.
                </div>
                <div class="card-glass p-4">
                    <h5>Manajemen Data Master</h5>
                    <p>Fitur CRUD Data Siswa & Guru (Simulasi).</p>
                    <button class="btn btn-primary"
                        onclick="Swal.fire('Info', 'Fitur ini dalam pengembangan V8', 'info')">Tambah Data
                        Siswa</button>
                </div>
            </div>

        </main>
    </div>

    <div class="modal fade" id="modalEditProfile" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content border-0 shadow-lg rounded-4">
                <div class="modal-header border-0 bg-light rounded-top-4">
                    <h5 class="modal-title fw-bold"><i class="fas fa-user-edit me-2"></i>Edit Profil Saya</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body p-4">
                    <div class="text-center mb-4">
                        <div class="position-relative d-inline-block">
                            <img src="" id="preview-foto" class="rounded-circle shadow-sm"
                                style="width: 120px; height: 120px; object-fit: cover; border: 4px solid white;">
                            <label for="input-foto"
                                class="btn btn-sm btn-dark position-absolute bottom-0 end-0 rounded-circle"
                                style="width:35px;height:35px;padding:6px;">
                                <i class="fas fa-camera"></i>
                            </label>
                            <input type="file" id="input-foto" class="d-none" accept="image/*"
                                onchange="previewImage()">
                        </div>
                        <div class="small text-muted mt-2">Ketuk ikon kamera untuk ubah foto</div>
                    </div>

                    <div class="form-floating mb-3">
                        <textarea class="form-control" placeholder="Tulis bio..." id="input-bio"
                            style="height: 80px"></textarea>
                        <label>Bio / Status Singkat</label>
                    </div>

                    <div class="row g-2">
                        <div class="col-md-6">
                            <div class="form-floating mb-3">
                                <input type="text" class="form-control" id="input-hobi" placeholder="Hobi">
                                <label>Hobi</label>
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="form-floating mb-3">
                                <input type="text" class="form-control" id="input-cita" placeholder="Cita-cita">
                                <label>Cita-Cita</label>
                            </div>
                        </div>
                    </div>

                    <div class="form-floating mb-3">
                        <input type="email" class="form-control" id="input-email" placeholder="Email">
                        <label>Alamat Email</label>
                    </div>

                    <div class="form-floating mb-3">
                        <input type="text" class="form-control" id="input-hp" placeholder="No HP">
                        <label>Nomor WhatsApp</label>
                    </div>
                </div>
                <div class="modal-footer border-0">
                    <button type="button" class="btn btn-light rounded-pill px-4" data-bs-dismiss="modal">Batal</button>
                    <button type="button" onclick="saveProfile()"
                        class="btn btn-primary rounded-pill px-4 fw-bold">Simpan Perubahan</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // --- 1. DATABASE LOKAL (DUMMY DATA) ---
        const DATA_SISWA = [
            "Adinda Nurhikmah", "Aditya Prawira Anwar", "Alfiano Junitama", "Amel Maela-ni", "Awaludin",
            "Chandra Dwi Purwanto", "Davin Yogi Setiawan", "Dwi Nurul Umayah", "Endang Wardana", "Faiz Mukhamad Kaysah",
            "Fanesah", "Fardan Nurdiansyah", "Farkhan Rizqi Aufa", "Firda Reva Syifa'ah", "Ihza Maulana Nurkhatib",
            "Inggrid Zahra Husaini", "M. Zacky Chaerul Azzam", "Moch Arya Sugalih", "Muhammad Hasan Najmi", "Muhammad Hilman Azzam",
            "Muhammad Bahari", "Muhammad Bashil Mukhlis", "Muhammad Lutfi", "Nurul Najmi Auliya", "Panji Hafiz Khaerani",
            "Rama Nur Farezh", "Rayya Eka Zahira", "Refan Kaesa Febriana Putra", "Rizafa Nur Ramadhan Guiwat", "Satya Fauzan",
            "Sri Hidayanti", "Suci Wulan Sari", "Widia Sari", "Zahidah Pauziah", "Zahra Cantika Putri", "Syahrul Maulidi Alif"
        ];

        const DATA_GURU = ["Pak Adang", "Ibu Isti", "Ibu Elis", "Pak Labib", "Pak Pajar", "Pak Nurwanto", "Pak Diyanton"];

        const JADWAL_MAPEL = [
            { hari: "Senin", mapel: "Matematika", jam: "07.00 - 09.00", guru: "Ibu Elis", status: "Wajib" },
            { hari: "Senin", mapel: "B. Inggris", jam: "09.30 - 11.00", guru: "Pak Diyanton", status: "Wajib" },
            { hari: "Selasa", mapel: "Produktif TKJ", jam: "07.00 - 12.00", guru: "Pak Adang", status: "Praktek" },
            { hari: "Rabu", mapel: "PKK", jam: "07.00 - 10.00", guru: "Pak Pajar", status: "Teori" },
            { hari: "Kamis", mapel: "Agama (PAI)", jam: "08.00 - 10.00", guru: "Pak Labib", status: "Wajib" },
            { hari: "Jumat", mapel: "Olahraga", jam: "07.00 - 09.00", guru: "Pak Dalim", status: "Lapangan" }
        ];

        // --- 2. GLOBAL VARIABLES ---
        let currentUser = {};
        let profileModalInstance;
        let html5QrcodeScanner = null;

        // --- 3. INITIALIZATION ---
        window.onload = function () {
            // Populate Dropdown Login
            const siswaSelect = document.getElementById('siswa-name');
            DATA_SISWA.forEach(nama => {
                let opt = document.createElement('option');
                opt.value = nama;
                opt.innerText = nama;
                siswaSelect.appendChild(opt);
            });

            const guruSelect = document.getElementById('guru-name');
            DATA_GURU.forEach(nama => {
                let opt = document.createElement('option');
                opt.value = nama;
                opt.innerText = nama;
                guruSelect.appendChild(opt);
            });

            // Set Tanggal Hari Ini
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('current-date').innerText = new Date().toLocaleDateString('id-ID', options);

            // Init Storage jika kosong
            if (!localStorage.getItem('siswa_profiles')) {
                localStorage.setItem('siswa_profiles', JSON.stringify({}));
            }

            // Init Modal Bootstrap
            profileModalInstance = new bootstrap.Modal(document.getElementById('modalEditProfile'));

            // Cek jika user refresh halaman tapi belum logout (Session persistence sederhana)
            // (Opsional: Di versi ini kita reset login agar aman)
        };

        // --- 4. LOGIN SYSTEM ---
        function toggleLoginInput() {
            const role = document.getElementById('role-select').value;
            const guruInput = document.getElementById('guru-input-group');
            const siswaInput = document.getElementById('siswa-input-group');

            guruInput.classList.add('hidden');
            siswaInput.classList.add('hidden');

            if (role === 'guru') guruInput.classList.remove('hidden');
            if (role === 'siswa') siswaInput.classList.remove('hidden');
        }

        function login() {
            const role = document.getElementById('role-select').value;

            if (!role) {
                Swal.fire({ icon: 'error', title: 'Oops...', text: 'Silakan pilih akses login terlebih dahulu!' });
                return;
            }

            currentUser.role = role;

            // Validasi Nama
            if (role === 'siswa') {
                const nama = document.getElementById('siswa-name').value;
                if (!nama) return Swal.fire('Error', 'Pilih nama siswa!', 'warning');
                currentUser.name = nama;

                // Load UI Siswa
                initSiswaUI();
                nav('siswa-home');

            } else if (role === 'guru') {
                const nama = document.getElementById('guru-name').value;
                if (!nama) return Swal.fire('Error', 'Pilih nama guru!', 'warning');
                currentUser.name = nama;

                // Load UI Guru
                initGuruUI();
                nav('guru-home');

            } else if (role === 'petugas') {
                currentUser.name = "Petugas Piket";
                nav('petugas-scan');

            } else if (role === 'admin') {
                currentUser.name = "Administrator";
                nav('admin-home');
            }

            // Update Topbar Info
            document.getElementById('user-name-display').innerText = currentUser.name;
            document.getElementById('user-role-display').innerText = role.toUpperCase();

            // Set Avatar Default di Topbar
            const profiles = JSON.parse(localStorage.getItem('siswa_profiles'));
            const myData = profiles[currentUser.name] || {};
            const avatar = myData.foto || `https://ui-avatars.com/api/?name=${currentUser.name}&background=random`;
            document.getElementById('topbar-img').src = avatar;

            // Show Sidebar Menu sesuai Role
            document.querySelectorAll('.menu-group').forEach(el => el.classList.add('hidden'));
            document.getElementById(`menu-${role}`).classList.remove('hidden');

            // Transisi Halaman
            document.getElementById('view-login').classList.add('hidden');
            document.getElementById('view-dashboard').classList.remove('hidden');

            Swal.fire({
                icon: 'success',
                title: 'Login Berhasil',
                text: `Selamat datang, ${currentUser.name}!`,
                timer: 1500,
                showConfirmButton: false
            });
        }

        function logout() {
            Swal.fire({
                title: 'Keluar Aplikasi?',
                text: "Anda harus login ulang untuk masuk.",
                icon: 'warning',
                showCancelButton: true,
                confirmButtonColor: '#3085d6',
                cancelButtonColor: '#d33',
                confirmButtonText: 'Ya, Keluar'
            }).then((result) => {
                if (result.isConfirmed) {
                    location.reload();
                }
            });
        }

        // --- 5. NAVIGATION SYSTEM (SPA FEEL) ---
        function nav(pageId) {
            // Hide all pages
            document.querySelectorAll('.page-section').forEach(el => el.classList.add('hidden'));
            // Remove active class from sidebar
            document.querySelectorAll('.nav-link-custom').forEach(el => el.classList.remove('active'));

            // Show target page
            const targetPage = document.getElementById(`page-${pageId}`);
            if (targetPage) {
                targetPage.classList.remove('hidden');

                // Add animation class re-trigger
                targetPage.classList.remove('fade-in');
                void targetPage.offsetWidth; // trigger reflow
                targetPage.classList.add('fade-in');
            }

            // Update Title
            const titles = {
                'siswa-home': 'Profil Siswa',
                'siswa-jadwal': 'Jadwal Pelajaran',
                'siswa-nilai': 'Kartu Hasil Studi',
                'guru-home': 'Dashboard Guru',
                'guru-nilai': 'Input Nilai Siswa',
                'petugas-scan': 'Scanner QR',
                'admin-home': 'Administrator'
            };
            document.getElementById('page-title').innerText = titles[pageId] || 'Dashboard';

            // Special Handler: Scanner
            if (pageId === 'petugas-scan') {
                startScanner();
            } else {
                stopScanner();
            }
        }

        // --- 6. SISWA FEATURES ---
        function initSiswaUI() {
            loadSiswaProfileData();
            loadSiswaJadwal();
            loadSiswaNilai();
        }

        function loadSiswaProfileData() {
            const profiles = JSON.parse(localStorage.getItem('siswa_profiles'));
            const data = profiles[currentUser.name] || {};

            // Default Values if Empty
            const bio = data.bio || "Siswa rajin SMKN 1 Lemahabang.";
            const hobi = data.hobi || "-";
            const cita = data.cita || "-";
            const email = data.email || "-";
            const hp = data.hp || "-";
            const foto = data.foto || `https://ui-avatars.com/api/?name=${currentUser.name}&background=random&size=256`;

            // Update DOM Elements
            document.getElementById('disp-nama').innerText = currentUser.name;
            document.getElementById('disp-bio').innerText = bio;
            document.getElementById('disp-hobi').innerText = hobi;
            document.getElementById('disp-cita').innerText = cita;
            document.getElementById('disp-email').innerText = email;
            document.getElementById('disp-hp').innerText = hp;
            document.getElementById('disp-foto').src = foto;
            document.getElementById('topbar-img').src = foto; // Sync Topbar

            // Generate QR Code
            const qrContainer = document.getElementById("my-qr-code");
            qrContainer.innerHTML = ""; // Clear old QR
            new QRCode(qrContainer, {
                text: currentUser.name + "|" + new Date().toISOString(), // Unique Data
                width: 150,
                height: 150,
                colorDark: "#000000",
                colorLight: "#ffffff",
                correctLevel: QRCode.CorrectLevel.H
            });
        }

        function loadSiswaJadwal() {
            const tbody = document.getElementById('tbody-jadwal-siswa');
            tbody.innerHTML = '';

            JADWAL_MAPEL.forEach((item, index) => {
                let badgeClass = item.status === 'Praktek' ? 'bg-warning' : (item.status === 'Wajib' ? 'bg-success' : 'bg-secondary');

                let row = `
                    <tr>
                        <td class="fw-bold">${item.hari}</td>
                        <td>${item.jam}</td>
                        <td class="fw-bold text-primary">${item.mapel}</td>
                        <td>${item.guru}</td>
                        <td><span class="badge ${badgeClass} rounded-pill">${item.status}</span></td>
                    </tr>
                `;
                tbody.innerHTML += row;
            });
        }

        function loadSiswaNilai() {
            const container = document.getElementById('container-nilai-siswa');
            container.innerHTML = '';
            const mapelList = ["Matematika", "B. Indonesia", "B. Inggris", "Produktif TKJ", "PKK", "Agama"];

            mapelList.forEach(mapel => {
                // Random Score Generator agar terlihat beda tiap mapel
                const tugas = Math.floor(Math.random() * (95 - 75) + 75);
                const uts = Math.floor(Math.random() * (90 - 70) + 70);
                const uas = Math.floor(Math.random() * (90 - 70) + 70);
                const rata = Math.round((tugas + uts + uas) / 3);

                let grade = rata >= 90 ? 'A' : (rata >= 80 ? 'B' : 'C');
                let color = grade === 'A' ? 'success' : (grade === 'B' ? 'primary' : 'warning');

                let cardHtml = `
                    <div class="col-md-4 mb-4">
                        <div class="card-glass h-100 border-start border-5 border-${color}">
                            <div class="p-3 d-flex justify-content-between align-items-center border-bottom">
                                <h6 class="fw-bold mb-0">${mapel}</h6>
                                <span class="badge bg-${color} rounded-circle p-2" style="width:35px;height:35px;display:flex;align-items:center;justify-content:center;">${grade}</span>
                            </div>
                            <div class="p-3">
                                <div class="d-flex justify-content-between mb-2"><small>Tugas</small> <b>${tugas}</b></div>
                                <div class="d-flex justify-content-between mb-2"><small>UTS</small> <b>${uts}</b></div>
                                <div class="d-flex justify-content-between mb-2"><small>UAS</small> <b>${uas}</b></div>
                                <hr class="my-2">
                                <div class="d-flex justify-content-between"><small class="fw-bold text-dark">Rata-rata</small> <b class="text-${color}">${rata}</b></div>
                            </div>
                        </div>
                    </div>
                `;
                container.innerHTML += cardHtml;
            });
        }

        // --- 7. EDIT PROFILE LOGIC ---
        function openEditProfile() {
            const profiles = JSON.parse(localStorage.getItem('siswa_profiles'));
            const data = profiles[currentUser.name] || {};

            // Fill Form with Current Data
            document.getElementById('input-bio').value = data.bio || "";
            document.getElementById('input-hobi').value = data.hobi || "";
            document.getElementById('input-cita').value = data.cita || "";
            document.getElementById('input-email').value = data.email || "";
            document.getElementById('input-hp').value = data.hp || "";
            document.getElementById('preview-foto').src = document.getElementById('disp-foto').src;

            profileModalInstance.show();
        }

        function previewImage() {
            const file = document.getElementById('input-foto').files[0];
            if (file) {
                const reader = new FileReader();
                reader.onloadend = function () {
                    document.getElementById('preview-foto').src = reader.result;
                }
                reader.readAsDataURL(file);
            }
        }

        function saveProfile() {
            const profiles = JSON.parse(localStorage.getItem('siswa_profiles'));

            // Construct New Data Object
            const newData = {
                bio: document.getElementById('input-bio').value,
                hobi: document.getElementById('input-hobi').value,
                cita: document.getElementById('input-cita').value,
                email: document.getElementById('input-email').value,
                hp: document.getElementById('input-hp').value,
                foto: document.getElementById('preview-foto').src // Simpan Base64 Image
            };

            // Save to LocalStorage
            profiles[currentUser.name] = newData;
            localStorage.setItem('siswa_profiles', JSON.stringify(profiles));

            // Update UI & Close Modal
            profileModalInstance.hide();
            loadSiswaProfileData();

            Swal.fire({
                icon: 'success',
                title: 'Tersimpan!',
                text: 'Profil kamu berhasil diperbarui.',
                timer: 1500
            });
        }

        // --- 8. GURU LOGIC ---
        function initGuruUI() {
            const tbody = document.getElementById('tbody-input-nilai');
            tbody.innerHTML = '';

            // Loop 10 siswa pertama saja sebagai sampel
            for (let i = 0; i < 10; i++) {
                let siswa = DATA_SISWA[i];
                let row = `
                    <tr>
                        <td class="fw-bold">${siswa}</td>
                        <td><input type="number" class="form-control form-control-sm text-center" value="${Math.floor(Math.random() * 10 + 80)}"></td>
                        <td><input type="number" class="form-control form-control-sm text-center" value="${Math.floor(Math.random() * 10 + 80)}"></td>
                        <td><input type="number" class="form-control form-control-sm text-center" value="${Math.floor(Math.random() * 10 + 75)}"></td>
                        <td><input type="number" class="form-control form-control-sm text-center" value="${Math.floor(Math.random() * 10 + 75)}"></td>
                        <td><button class="btn btn-sm btn-primary" onclick="simpanNilai('${siswa}')"><i class="fas fa-save"></i></button></td>
                    </tr>
                `;
                tbody.innerHTML += row;
            }
        }

        function simpanNilai(nama) {
            const Toast = Swal.mixin({
                toast: true,
                position: 'top-end',
                showConfirmButton: false,
                timer: 2000,
                timerProgressBar: true
            });
            Toast.fire({
                icon: 'success',
                title: `Nilai ${nama} disimpan!`
            });
        }

        // --- 9. SCANNER LOGIC (PETUGAS) ---
        function startScanner() {
            if (html5QrcodeScanner === null) {
                // Initialize Scanner
                html5QrcodeScanner = new Html5QrcodeScanner(
                    "reader",
                    { fps: 10, qrbox: { width: 250, height: 250 } },
                    /* verbose= */ false
                );
                html5QrcodeScanner.render(onScanSuccess, onScanFailure);
            }
        }

        function stopScanner() {
            if (html5QrcodeScanner) {
                html5QrcodeScanner.clear().catch(error => {
                    console.error("Failed to clear html5QrcodeScanner. ", error);
                });
                html5QrcodeScanner = null;
            }
        }

        function onScanSuccess(decodedText, decodedResult) {
            // Mainkan Audio Beep
            // const beep = new Audio('beep.mp3'); // jika ada file

            document.getElementById('scan-result').innerHTML = `Terdeteksi: ${decodedText}`;

            Swal.fire({
                title: 'Absensi Berhasil!',
                html: `<h3 class="text-primary">${decodedText.split('|')[0]}</h3><p>Waktu: ${new Date().toLocaleTimeString()}</p>`,
                icon: 'success',
                timer: 2000,
                showConfirmButton: false
            });

            // Bisa tambahkan logika simpan ke localStorage log absensi disini
        }

        function onScanFailure(error) {
            // handle scan failure, usually better to ignore and keep scanning.
            // console.warn(`Code scan error = ${error}`);
        }

    </script>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>

</html>
