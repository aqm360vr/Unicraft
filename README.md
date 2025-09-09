<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unicraft - Peluang Pelaburan</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals with Professional Blue -->
    <!-- Application Structure Plan: A single-page, scrollable dashboard with a sticky navigation bar that mirrors the pitch flow (Executive Summary, Branding, Services, Marketing, Equipment, Staffing, Operations, Financials, Risks, Growth, Next Steps). This linear, scrollable structure is chosen to guide the investor through a complete narrative, from the problem statement to the financial ask and future plans, making the entire proposal feel cohesive and professional. Key interactions include the navigation and a dynamic chart for investment breakdown. -->
    <!-- Visualization & Content Choices: 
        1. Executive Summary: Report Info (Problem, Solution) -> Goal (Hook, Summarize) -> Presentation (Bolded text with clear headings) -> Interaction (None) -> Justification (Provides a quick, scannable overview for busy investors) -> Library (HTML/CSS with Tailwind).
        2. Investment Breakdown: Report Info (Registration, Bank Account, Equipment, Fit-out, Working Capital) -> Goal (Inform, Justify Ask) -> Viz (Doughnut Chart) -> Interaction (Hover for details) -> Justification (Visually breaks down the total investment into clear categories, more impactful than a simple list) -> Library (Chart.js/Canvas).
        3. Pricing & Costs: Report Info (Sample prices, monthly salaries) -> Goal (Persuade, Justify) -> Presentation (Bullet points with clear financial figures) -> Interaction (None) -> Justification (Presents a clear, scannable summary of the business's financial viability) -> Library (HTML/CSS with Tailwind).
        4. Other sections (Services, Marketing, Risks, etc.): Report Info (Lists) -> Goal (Inform, Organize) -> Presentation (Card-based lists with headings) -> Interaction (None) -> Justification (Breaks down complex information into digestible, easy-to-read segments) -> Library (HTML/CSS with Tailwind).
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: #2563eb;
        }
        .active-link {
            color: #2563eb;
            font-weight: 600;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <header id="header" class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <h1 class="text-2xl font-bold text-gray-900">Unicraft</h1>
            <div class="hidden lg:flex space-x-8 text-sm">
                <a href="#ringkasan-eksekutif" class="nav-link text-gray-600">Ringkasan</a>
                <a href="#penjenamaan" class="nav-link text-gray-600">Penjenamaan</a>
                <a href="#perkhidmatan" class="nav-link text-gray-600">Perkhidmatan</a>
                <a href="#pemasaran" class="nav-link text-gray-600">Pemasaran</a>
                <a href="#peralatan-staf" class="nav-link text-gray-600">Peralatan & Staf</a>
                <a href="#operasi" class="nav-link text-gray-600">Operasi</a>
                <a href="#kewangan" class="nav-link text-gray-600">Kewangan</a>
                <a href="#risiko-pertumbuhan" class="nav-link text-gray-600">Risiko & Pertumbuhan</a>
                <a href="#langkah-seterusnya" class="nav-link text-gray-600">Langkah Seterusnya</a>
            </div>
            <a href="#langkah-seterusnya" class="bg-blue-600 text-white px-4 py-2 rounded-lg font-semibold hover:bg-blue-700 transition">Sertai Kami</a>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-12">

        <section id="ringkasan-eksekutif" class="text-center py-16 md:py-24">
            <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">Unicraft: Peluang Pelaburan di UNIMAS</h2>
            <p class="text-xl text-gray-600 max-w-3xl mx-auto mb-8">
                Unicraft will be a campus-facing print & service hub for students, staff and nearby community.
            </p>
            <div class="bg-white p-6 rounded-xl shadow-md inline-block">
                <p class="text-gray-700">Dicadangkan oleh:</p>
                <p class="text-xl font-semibold text-blue-600">Slyvester Ulla, FSSK</p>
            </div>
        </section>
        
        <section id="ringkasan-eksekutif-detail" class="py-16 md:py-20 bg-gray-100 -mx-6 px-6 rounded-xl">
            <div class="grid md:grid-cols-2 gap-8 text-center md:text-left">
                <div>
                    <h3 class="text-3xl font-bold text-gray-900 mb-4">Masalah</h3>
                    <p class="text-lg text-gray-700">Pelajar & kakitangan kampus memerlukan akses pantas dan boleh dipercayai untuk cetakan, fotokopi, binding, laminasi dan perkhidmatan internet.</p>
                </div>
                <div>
                    <h3 class="text-3xl font-bold text-gray-900 mb-4">Penyelesaian</h3>
                    <p class="text-lg text-gray-700">Unicraft - sebuah kedai serba ada di lokasi strategik dalam/berdekatan UNIMAS yang menawarkan harga kompetitif, cepat dan mesra pelajar.</p>
                </div>
            </div>
        </section>

        <section id="penjenamaan" class="py-16 md:py-20">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Strategi Penjenamaan</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Kami membina identiti jenama yang mudah diingati dan disesuaikan dengan persekitaran kampus.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-2xl font-bold text-blue-600 mb-3">Nama Jenama Utama</h4>
                    <p class="text-gray-700 font-semibold">Print@UNIMAS & Print@HEPA</p>
                    <p class="text-sm text-gray-500 mt-2">Nama-nama ini mewujudkan identiti lokal yang mudah diingati dan diyakini oleh komuniti kampus.</p>
                </div>
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-2xl font-bold text-green-600 mb-3">Janji Jenama</h4>
                    <ul class="list-disc list-inside text-lg text-gray-700 font-semibold">
                        <li>Cepat</li>
                        <li>Berpatutan</li>
                        <li>Mesra Pelajar</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="perkhidmatan" class="py-16 md:py-20 bg-gray-100 -mx-6 px-6 rounded-xl">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Perkhidmatan Teras</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Kami menawarkan rangkaian perkhidmatan yang komprehensif, disesuaikan untuk memenuhi keperluan harian komuniti UNIMAS.</p>
            </div>
            <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-6 text-center">
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="text-4xl">📄</span>
                    <h5 class="font-semibold mt-2">Percetakan Warna</h5>
                    <p class="text-sm text-gray-500">A4 / A3</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="text-4xl">📠</span>
                    <h5 class="font-semibold mt-2">Fotokopi</h5>
                    <p class="text-sm text-gray-500">A4 / A3 (B&W & Warna)</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="text-4xl">📚</span>
                    <h5 class="font-semibold mt-2">Penjilidan</h5>
                     <p class="text-sm text-gray-500">Staple, comb, coil</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <span class="text-4xl">🛡️</span>
                    <h5 class="font-semibold mt-2">Laminasi</h5>
                     <p class="text-sm text-gray-500">A4 / A3</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md col-span-2 md:col-span-1">
                    <span class="text-4xl">🌐</span>
                    <h5 class="font-semibold mt-2">Perkhidmatan Internet</h5>
                    <p class="text-sm text-gray-500">Cetakan dari USB & email</p>
                </div>
            </div>
        </section>

        <section id="pemasaran" class="py-16 md:py-20">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Pemasaran & Kolateral Awal</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Alat pemasaran awal kami akan memberi tumpuan kepada kehadiran fizikal di kawasan kampus.</p>
            </div>
            <ul class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <li class="bg-white p-6 rounded-xl shadow-lg border border-gray-200">
                    <p class="font-semibold">Papan Tanda / Signage</p>
                    <p class="text-sm text-gray-600">Utama di fasad perniagaan.</p>
                </li>
                <li class="bg-white p-6 rounded-xl shadow-lg border border-gray-200">
                    <p class="font-semibold">Bunting</p>
                    <p class="text-sm text-gray-600">Untuk kempen dan promosi semester.</p>
                </li>
                <li class="bg-white p-6 rounded-xl shadow-lg border border-gray-200">
                    <p class="font-semibold">Brosur / Flyer</p>
                    <p class="text-sm text-gray-600">Pek selamat datang untuk pelajar baharu.</p>
                </li>
            </ul>
        </section>
        
        <section id="peralatan-staf" class="py-16 md:py-20 bg-gray-100 -mx-6 px-6 rounded-xl">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Peralatan & Pelan Sumber Manusia</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Kami akan melabur dalam peralatan yang boleh dipercayai dan pasukan yang cekap untuk menyokong operasi.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-xl font-bold text-gray-900 mb-4">Peralatan Utama (Contoh)</h4>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        <li>A3 colour multifunction printer</li>
                        <li>B&W backup photocopier</li>
                        <li>Binding machine (comb/coil)</li>
                        <li>Laminator & PC / POS system</li>
                        <li>Furniture & fit-out materials</li>
                    </ul>
                </div>
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-xl font-bold text-gray-900 mb-4">Pelan Staf & HR</h4>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        <li>**Pengurus:** RM2,500 – RM3,500 / bulan.</li>
                        <li>**Pelajar JOC:** RM4.00 / jam (maksimum 10 jam/minggu).</li>
                        <li>**Struktur Harian:** Pengurus + 1–2 pelajar semasa waktu puncak.</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="operasi" class="py-16 md:py-20">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Rancangan Operasi</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Struktur operasi kami yang cekap memastikan perkhidmatan yang boleh dipercayai dan konsisten untuk pelanggan kami.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-xl font-bold mb-4">Waktu Operasi</h4>
                    <p class="text-lg text-gray-700">Waktu perniagaan kami sejajar dengan waktu puncak aktiviti universiti.</p>
                    <div class="mt-4">
                        <p class="font-semibold">🗓️ Isnin - Jumaat</p>
                        <p class="font-semibold">🕗 8:00 AM - 5:00 PM</p>
                    </div>
                </div>
                 <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-xl font-bold mb-4">Aliran Kerja & Pembayaran</h4>
                    <p class="text-gray-700">Aliran kerja yang ringkas untuk kecekapan maksimum.</p>
                    <ul class="mt-4 list-disc list-inside space-y-2 text-gray-700">
                        <li>**Aliran Kerja:** Terima fail digital/USB → cetak → binding/laminate → serah</li>
                        <li>**Pembayaran:** Tunai & kaedah e-wallet / QR</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="kewangan" class="py-16 md:py-20 bg-blue-50 -mx-6 px-6 rounded-xl">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Analisis Kewangan & ROI</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Unjuran ini memberikan gambaran tentang potensi Unicraft untuk menjana pendapatan dan memberikan pulangan yang menguntungkan.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-8 items-start">
                <div>
                    <h4 class="text-xl font-bold mb-4">Pecahan Kos Pelaburan Awal</h4>
                    <p class="text-gray-700 mb-6">Pelaburan sebanyak **RM45,000** akan membiayai kos permulaan utama.</p>
                    <ul class="space-y-2 text-gray-800">
                        <li class="flex items-center"><span class="h-4 w-4 rounded-full bg-blue-500 mr-3"></span> CAPEX (Peralatan & Fit-out): RM24,400</li>
                        <li class="flex items-center"><span class="h-4 w-4 rounded-full bg-indigo-500 mr-3"></span> Modal Kerja & Pelancaran: RM3,600</li>
                        <li class="flex items-center"><span class="h-4 w-4 rounded-full bg-purple-500 mr-3"></span> Modal Operasi 3 Bulan: RM18,000</li>
                    </ul>
                </div>
                <div class="chart-container">
                    <canvas id="investmentChart"></canvas>
                </div>
            </div>
            <div class="mt-12">
                <h4 class="text-2xl font-bold text-gray-900 mb-4 text-center">Unjuran Pendapatan & Titik Pulang Modal</h4>
                <div class="grid md:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-xl shadow-lg border border-gray-200 text-center">
                        <h5 class="text-xl font-bold text-gray-900 mb-2">Senario Konservatif</h5>
                        <p class="text-sm text-gray-600">40 transaksi/hari × RM3 AOV</p>
                        <p class="text-lg font-semibold mt-2">Hasil Bulanan: ~ RM2,640</p>
                        <p class="text-red-600 font-bold mt-2">Kerugian</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-lg border border-gray-200 text-center">
                        <h5 class="text-xl font-bold text-gray-900 mb-2">Senario Asas</h5>
                        <p class="text-sm text-gray-600">80 transaksi/hari × RM5 AOV</p>
                        <p class="text-lg font-semibold mt-2">Hasil Bulanan: ~ RM8,800</p>
                        <p class="text-green-600 font-bold mt-2">ROI 1 Tahun: ~26%</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-lg border border-gray-200 text-center">
                        <h5 class="text-xl font-bold text-gray-900 mb-2">Senario Agresif</h5>
                        <p class="text-sm text-gray-600">150 transaksi/hari × RM7 AOV</p>
                        <p class="text-lg font-semibold mt-2">Hasil Bulanan: ~ RM23,100</p>
                        <p class="text-green-600 font-bold mt-2">ROI 1 Tahun: ~312%</p>
                    </div>
                </div>
                <div class="mt-8 text-center text-sm text-gray-500 italic">
                    <p>Titik pulang modal dijangka pada 6-12 bulan. Contohnya, pada RM5 AOV, titik pulang modal berlaku pada kira-kira 69 transaksi/hari.</p>
                </div>
            </div>
        </section>

        <section id="risiko-pertumbuhan" class="py-16 md:py-20">
            <div class="text-center mb-12">
                <h3 class="text-3xl font-bold text-gray-900">Risiko & Peluang Pertumbuhan</h3>
                <p class="text-md text-gray-600 mt-2 max-w-2xl mx-auto">Kami telah mengenal pasti potensi cabaran dan merangka strategi untuk mengurangkannya dan memaksimumkan pulangan.</p>
            </div>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-2xl font-bold text-red-600 mb-3">Risiko</h4>
                    <ul class="list-disc list-inside text-gray-700">
                        <li>Persaingan berhampiran kampus</li>
                        <li>Tekanan harga</li>
                        <li>Masa henti peralatan</li>
                    </ul>
                </div>
                <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-200">
                    <h4 class="text-2xl font-bold text-green-600 mb-3">Peluang Pertumbuhan</h4>
                    <ul class="list-disc list-inside text-gray-700">
                        <li>Perkongsian dengan persatuan pelajar</li>
                        <li>Tawaran pakej semester & jualan alat tulis</li>
                        <li>Kembangkan perkhidmatan kepada acara & fakulti</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="langkah-seterusnya" class="py-16 md:py-20 text-center">
            <h3 class="text-3xl font-bold text-gray-900 mb-4">Langkah Seterusnya</h3>
            <p class="text-lg text-gray-700 max-w-3xl mx-auto mb-8">Kami menjemput anda untuk membincangkan peluang pelaburan ini dengan lebih lanjut.</p>
            <ol class="list-decimal list-inside space-y-3 text-left max-w-md mx-auto">
                <li>Dapatkan sebut harga pembekal untuk peralatan dan kelengkapan.</li>
                <li>Sahkan terma sewa/permit dengan UNIMAS.</li>
                <li>Muktamadkan struktur pendanaan pelabur.</li>
                <li>Tandatangani perjanjian pelaburan dan mulakan persediaan.</li>
            </ol>
            <div class="mt-12 bg-blue-600 text-white p-6 rounded-xl shadow-lg inline-block">
                <h4 class="text-xl font-bold mb-2">Hubungi Slyvester Ulla</h4>
                <p class="font-semibold">Fakulti Sains Sosial dan Kemanusiaan (FSSK)</p>
            </div>
        </section>

    </main>
    
    <footer class="bg-gray-800 text-white mt-12">
        <div class="container mx-auto px-6 py-8 text-center">
            <p class="text-sm text-gray-400">© Unicraft. All rights reserved.</p>
        </div>
    </footer>
    
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const ctx = document.getElementById('investmentChart').getContext('2d');
            const investmentChart = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: ['CAPEX (Peralatan & Fit-out)', 'Modal Kerja & Pelancaran', 'Modal Operasi 3 Bulan'],
                    datasets: [{
                        label: 'Pecahan Kos Pelaburan (Anggaran)',
                        data: [24400, 3600, 18000],
                        backgroundColor: [
                            '#3b82f6',
                            '#6366f1',
                            '#8b5cf6'
                        ],
                        borderColor: '#f9fafb',
                        borderWidth: 4,
                        hoverOffset: 8
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    cutout: '60%',
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed !== null) {
                                        label += 'RM' + context.parsed.toLocaleString('ms-MY');
                                    }
                                    return label;
                                }
                            }
                        }
                    }
                }
            });

            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');

            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.4
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.remove('active-link');
                            if (link.getAttribute('href').substring(1) === entry.target.id) {
                                link.classList.add('active-link');
                            }
                        });
                    }
                });
            }, observerOptions);

            sections.forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
