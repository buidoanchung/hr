<BÙI ĐOÀN CHUNG>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toàn Cảnh Thị Trường Lao Động Việt Nam 2025</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: A user-centric, dashboard-style SPA designed to tell the story of the labor market. The flow starts with high-level key indicators, then dives deep into thematic sections: 1. Overall Labor & Employment (The Big Picture), 2. Unemployment Hotspots (The Core Challenge), 3. Business Health (The Duality of Growth & Struggle), 4. Future Trends (Actionable Insights), and 5. Recommendations (Practical Advice). This structure prioritizes understanding and exploration over the report's linear format, guiding users from general context to specific, impactful findings and actionable takeaways. -->
    <!-- Visualization & Content Choices: 
        - Key Indicators: Goal: Inform. Method: Styled stat cards. Justification: Provides a quick, digestible snapshot.
        - Unemployment Comparison: Goal: Compare. Method: Interactive Bar Chart (Chart.js). Interaction: Buttons to toggle between General and Youth data. Justification: Visually highlights the critical issue of youth unemployment, the report's most striking finding.
        - Business Entry vs. Exit: Goal: Compare. Method: Side-by-side stat cards with bar visuals. Justification: Immediately conveys the intense market competition.
        - High-Demand Industries: Goal: Organize/Inform. Method: Interactive clickable cards. Interaction: Click to reveal details. Justification: More engaging and user-friendly than a static list.
        - Labor Force Sectors: Goal: Inform. Method: Donut chart (Chart.js). Justification: Clear representation of workforce composition.
        - Recommendations: Goal: Organize. Method: Tabbed interface. Justification: Neatly separates advice for different audiences.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8F7F4;
            color: #333333;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .nav-button {
            transition: all 0.3s ease;
        }
        .nav-button.active {
            background-color: #4A908A;
            color: white;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
        }
        .tab-button.active {
            border-bottom: 3px solid #4A908A;
            color: #4A908A;
            font-weight: 600;
        }
        .job-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }
        .job-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="antialiased">
    <header class="bg-white shadow-sm sticky top-0 z-50">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-[#4A908A]">
                <span class="hidden sm:inline">Báo Cáo Tương Tác:</span> Lao Động 2025
            </h1>
            <div class="hidden md:flex space-x-2">
                <a href="#overview" class="nav-button text-gray-600 hover:bg-gray-200 px-3 py-2 rounded-md text-sm font-medium">Tổng Quan</a>
                <a href="#unemployment" class="nav-button text-gray-600 hover:bg-gray-200 px-3 py-2 rounded-md text-sm font-medium">Thất Nghiệp</a>
                <a href="#business" class="nav-button text-gray-600 hover:bg-gray-200 px-3 py-2 rounded-md text-sm font-medium">Doanh Nghiệp</a>
                <a href="#trends" class="nav-button text-gray-600 hover:bg-gray-200 px-3 py-2 rounded-md text-sm font-medium">Xu Hướng</a>
                <a href="#recommendations" class="nav-button text-gray-600 hover:bg-gray-200 px-3 py-2 rounded-md text-sm font-medium">Khuyến Nghị</a>
            </div>
            <div class="md:hidden">
                 <select id="mobile-nav" class="block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50">
                    <option value="#overview">Tổng Quan</option>
                    <option value="#unemployment">Thất Nghiệp</option>
                    <option value="#business">Doanh Nghiệp</option>
                    <option value="#trends">Xu Hướng</option>
                    <option value="#recommendations">Khuyến Nghị</option>
                </select>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">
        <section class="text-center mb-12 md:mb-16 fade-in">
            <h2 class="text-3xl md:text-5xl font-extrabold text-[#333333] mb-3">Toàn Cảnh Thị Trường Lao Động Việt Nam 2025</h2>
            <p class="text-lg md:text-xl text-gray-600 max-w-3xl mx-auto">Phân tích tương tác dựa trên báo cáo của AI do <span class="font-semibold text-[#4A908A]">Nghề Nhân sự Việt Nam (NNS)</span>. 
            Khám phá các số liệu, xu hướng và thách thức định hình thị trường.</p>
        </section>

        <section id="key-indicators" class="mb-12 md:mb-16">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-6">
                <div class="bg-white p-4 rounded-xl shadow-md text-center fade-in">
                    <p class="text-sm font-medium text-gray-500">Lực lượng lao động</p>
                    <p class="text-2xl md:text-3xl font-bold text-[#4A908A]">52,9</p>
                    <p class="text-sm text-gray-500">triệu người (Q1/2025)</p>
                </div>
                <div class="bg-white p-4 rounded-xl shadow-md text-center fade-in" style="animation-delay: 0.1s;">
                    <p class="text-sm font-medium text-gray-500">Tỷ lệ thất nghiệp</p>
                    <p class="text-2xl md:text-3xl font-bold text-[#D0A04C]">2,20%</p>
                    <p class="text-sm text-gray-500">trong độ tuổi lao động</p>
                </div>
                <div class="bg-white p-4 rounded-xl shadow-md text-center fade-in" style="animation-delay: 0.2s;">
                    <p class="text-sm font-medium text-gray-500">Tăng trưởng FDI</p>
                    <p class="text-2xl md:text-3xl font-bold text-[#4A908A]">+51,2%</p>
                    <p class="text-sm text-gray-500">vốn đăng ký (5 tháng)</p>
                </div>
                <div class="bg-white p-4 rounded-xl shadow-md text-center fade-in" style="animation-delay: 0.3s;">
                    <p class="text-sm font-medium text-gray-500">Lao động qua đào tạo</p>
                    <p class="text-2xl md:text-3xl font-bold text-[#4A908A]">28,8%</p>
                    <p class="text-sm text-gray-500">có bằng, chứng chỉ</p>
                </div>
            </div>
        </section>

        <div class="space-y-16 md:space-y-24">
            <section id="overview" class="fade-in">
                <h3 class="text-2xl md:text-3xl font-bold text-center mb-2">Bức Tranh Tổng Quan</h3>
                <p class="text-gray-600 text-center max-w-3xl mx-auto mb-8">Năm 2025 chứng kiến sự mở rộng quy mô lực lượng lao động so với cùng kỳ, đi kèm với sự cải thiện về chất lượng. Tuy nhiên, tỷ lệ lao động phi chính thức vẫn là một thách thức lớn, ảnh hưởng đến tính bền vững của việc làm và thị trường đầu năm 2025.</p>
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                    <div class="lg:col-span-2 bg-white p-4 sm:p-6 rounded-xl shadow-lg">
                        <div class="chart-container">
                            <canvas id="laborForceChart"></canvas>
                        </div>
                    </div>
                    <div class="space-y-4">
                        <div class="bg-white p-6 rounded-xl shadow-lg">
                            <h4 class="font-bold text-lg mb-2 text-[#4A908A]">💡 Chất lượng cải thiện</h4>
                            <p class="text-gray-700">Tỷ lệ lao động qua đào tạo có bằng, chứng chỉ đạt <span class="font-bold">28,8%</span>, tăng <span class="font-bold">1,0 điểm %</span> so với cùng kỳ năm trước, cho thấy nỗ lực nâng cao trình độ chuyên môn của nguồn nhân lực.</p>
                        </div>
                        <div class="bg-white p-6 rounded-xl shadow-lg">
                            <h4 class="font-bold text-lg mb-2 text-[#D0A04C]">⚠️ Thách thức tồn tại</h4>
                            <p class="text-gray-700">Tỷ lệ lao động phi chính thức vẫn ở mức cao <span class="font-bold">64,3%</span>. Con số này đặc biệt cao ở khu vực nông thôn (<span class="font-bold">74,2%</span>), đặt ra vấn đề về an sinh xã hội và quyền lợi người lao động.</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="unemployment" class="fade-in">
                <h3 class="text-2xl md:text-3xl font-bold text-center mb-2">Điểm Nóng Thất Nghiệp: Lao Động Trẻ</h3>
                <p class="text-gray-600 text-center max-w-3xl mx-auto mb-8">Mặc dù tỷ lệ thất nghiệp chung được duy trì ở mức thấp, tình hình của lao động trẻ (15-24 tuổi) lại là một câu chuyện hoàn toàn khác, đặc biệt ở khu vực thành thị. Điều này cho thấy sự "lệch pha" giữa đào tạo và nhu cầu thực tế của thị trường.</p>
                <div class="bg-white p-4 sm:p-6 rounded-xl shadow-lg">
                    <div class="text-center mb-6">
                        <div class="inline-flex rounded-md shadow-sm" role="group">
                            <button type="button" id="btnGeneralUnemployment" class="nav-button active px-4 py-2 text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-l-lg hover:bg-gray-100">
                                Thị trường
                            </button>
                            <button type="button" id="btnYouthUnemployment" class="nav-button px-4 py-2 text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-r-md hover:bg-gray-100">
                                Thanh niên (15-24)
                            </button>
                        </div>
                    </div>
                    <div class="chart-container">
                        <canvas id="unemploymentChart"></canvas>
                    </div>
                </div>
            </section>

            <section id="business" class="fade-in">
                <h3 class="text-2xl md:text-3xl font-bold text-center mb-2">Sức Khỏe Doanh Nghiệp: Tăng Trưởng & Sàng Lọc</h3>
                <p class="text-gray-600 text-center max-w-3xl mx-auto mb-8">Môi trường kinh doanh 2025 đầy năng động nhưng cũng vô cùng khắc nghiệt. Số doanh nghiệp gia nhập thị trường gần như tương đương với số rút lui, cho thấy một quá trình "thanh lọc" đang diễn ra mạnh mẽ.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <div class="bg-white p-6 rounded-xl shadow-lg text-center">
                        <h4 class="text-lg font-semibold mb-2">Doanh Nghiệp Gia Nhập</h4>
                        <p class="text-4xl font-bold text-green-600">~111,8 <span class="text-2xl">nghìn</span></p>
                        <p class="text-gray-500 mt-1">trong 5 tháng đầu năm 2025</p>
                        <p class="mt-4 text-gray-700">Trung bình mỗi tháng có gần <span class="font-bold">22,4 nghìn</span> doanh nghiệp mới và quay lại hoạt động.</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-lg text-center">
                        <h4 class="text-lg font-semibold mb-2">Doanh Nghiệp Rút Lui</h4>
                        <p class="text-4xl font-bold text-red-600">~111,6 <span class="text-2xl">nghìn</span></p>
                        <p class="text-gray-500 mt-1">trong 5 tháng đầu năm 2025</p>
                        <p class="mt-4 text-gray-700">Trung bình mỗi tháng có <span class="font-bold">22,3 nghìn</span> doanh nghiệp rời thị trường do cạnh tranh và khó khăn.</p>
                    </div>
                </div>
                 <div class="mt-8 bg-white p-6 rounded-xl shadow-lg">
                    <h4 class="text-xl font-bold text-center mb-4 text-[#4A908A]">Động Lực Tăng Trưởng Từ Vốn FDI</h4>
                    <p class="text-center text-gray-600 mb-6">Dòng vốn đầu tư nước ngoài (FDI) là điểm sáng nổi bật, khẳng định sức hấp dẫn của môi trường đầu tư Việt Nam và hứa hẹn tạo ra nhiều việc làm chất lượng cao.</p>
                     <div class="chart-container h-64 sm:h-80">
                         <canvas id="fdiChart"></canvas>
                     </div>
                </div>
            </section>
            
            <section id="trends" class="fade-in">
                <h3 class="text-2xl md:text-3xl font-bold text-center mb-2">Xu Hướng Tương Lai: Ngành "Hot" & Kỹ Năng Vàng</h3>
                <p class="text-gray-600 text-center max-w-3xl mx-auto mb-8">Thị trường đang có nhu cầu cao ở các ngành thâm dụng công nghệ và dịch vụ. Để nắm bắt cơ hội, người lao động cần trang bị các kỹ năng phù hợp, trong khi doanh nghiệp cần thấu hiểu kỳ vọng thay đổi của nhân viên, đặc biệt là thế hệ Z.</p>
                
                <div class="mb-12">
                     <h4 class="text-xl font-bold text-center mb-6">Các Ngành Dẫn Dắt Nhu Cầu Tuyển Dụng</h4>
                     <div id="jobTrendsContainer" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                     </div>
                </div>

                <div>
                    <h4 class="text-xl font-bold text-center mb-6">Kỹ Năng Then Chốt Thị Trường Cần</h4>
                    <div class="bg-white p-6 rounded-xl shadow-lg grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
                        <div class="border-b md:border-b-0 md:border-r border-gray-200 pb-4 md:pb-0 md:pr-6">
                            <p class="text-3xl mb-2">💻</p>
                            <h5 class="font-bold text-[#4A908A]">Kỹ năng số & Công nghệ</h5>
                            <p class="text-sm text-gray-600">AI tạo sinh, Phân tích dữ liệu, An ninh mạng, Điện toán đám mây.</p>
                        </div>
                        <div class="border-b md:border-b-0 md:border-r border-gray-200 pb-4 md:pb-0 md:pr-6">
                            <p class="text-3xl mb-2">🤝</p>
                            <h5 class="font-bold text-[#4A908A]">Kỹ năng mềm</h5>
                            <p class="text-sm text-gray-600">Giao tiếp, Giải quyết vấn đề, Tư duy chiến lược, Thích ứng nhanh.</p>
                        </div>
                        <div>
                            <p class="text-3xl mb-2">🌐</p>
                             <h5 class="font-bold text-[#4A908A]">Kỹ năng Toàn cầu</h5>
                             <p class="text-sm text-gray-600">Ngoại ngữ (đặc biệt là tiếng Anh), Hiểu biết đa văn hóa, Kỹ năng đối tác kinh doanh.</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="recommendations" class="fade-in">
                <h3 class="text-2xl md:text-3xl font-bold text-center mb-2">Khuyến Nghị Chiến Lược</h3>
                <p class="text-gray-600 text-center max-w-3xl mx-auto mb-8">Để điều hướng thành công trong thị trường lao động nhiều biến động, cả doanh nghiệp và người lao động đều cần có những chiến lược chủ động và linh hoạt.</p>
                <div class="bg-white rounded-xl shadow-lg p-4 sm:p-6">
                    <div class="border-b border-gray-200 mb-4">
                        <nav class="-mb-px flex justify-center space-x-4 md:space-x-8" aria-label="Tabs">
                            <button class="tab-button whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm md:text-base active" data-tab="for-business">
                                Cho Doanh nghiệp
                            </button>
                            <button class="tab-button whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm md:text-base text-gray-500 hover:text-gray-700 hover:border-gray-300" data-tab="for-employee">
                                Cho Người lao động
                            </button>
                        </nav>
                    </div>
                    <div id="tab-content">
                    </div>
                </div>
            </section>
        </div>
    </main>

    <footer class="bg-gray-800 text-white mt-16">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-6 text-center text-sm">
            <p>&copy; 2025. Ứng dụng web tương tác được phát triển dựa trên "Báo cáo thị trường lao động Việt Nam" của Nghề Nhân sự Việt Nam (NNS).</p>
            <p class="text-gray-400 mt-1">Dữ liệu được sử dụng cho mục đích phân tích và minh họa.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const laborData = {
                labels: ['Q1/2024', 'Q1/2025'],
                force: [52.9 - 0.532, 52.9],
                employed: [51.9 - 0.5321, 51.9]
            };

            const unemploymentData = {
                general: {
                    labels: ['Chung', 'Thành thị', 'Nông thôn'],
                    values: [2.20, 2.38, 1.98]
                },
                youth: {
                    labels: ['Chung (15-24)', 'Thành thị (15-24)', 'Nông thôn (15-24)'],
                    values: [7.93, 11.06, 6.32]
                }
            };

            const fdiData = {
                labels: ['5 tháng đầu 2024', '5 tháng đầu 2025'],
                values: [18.39 / (1 + 0.512), 18.39]
            };
            
            const jobTrendsData = [
                {
                    title: 'Công nghệ thông tin',
                    icon: '💻',
                    skills: ['AI Engineer', 'Data Scientist', 'Cybersecurity', 'DevOps']
                },
                {
                    title: 'Digital Marketing',
                    icon: '📈',
                    skills: ['SEO/SEM', 'Content Marketing', 'Data Analysis', 'Strategy']
                },
                {
                    title: 'Logistics & Chuỗi cung ứng',
                    icon: '🚚',
                    skills: ['Supply Chain Mgt.', 'Warehouse Mgt.', 'Import/Export', 'Coordination']
                },
                {
                    title: 'Chăm sóc sức khỏe',
                    icon: '❤️',
                    skills: ['Điều dưỡng', 'Phục hồi chức năng', 'Quản lý y tế']
                },
                {
                    title: 'Phát triển bền vững',
                    icon: '🌿',
                    skills: ['CSR', 'Environmental Mgt.', 'Sustainability Reporting']
                },
                {
                    title: 'Nhân sự (HR)',
                    icon: '👥',
                    skills: ['HR Business Partner', 'Talent Acquisition', 'C&B', 'HR Tech']
                }
            ];

            const recommendationsData = {
                'for-business': `
                    <ul class="space-y-4 list-disc list-inside text-gray-700 fade-in">
                        <li><strong>Thu hút & Giữ chân nhân tài:</strong> Xây dựng thương hiệu nhà tuyển dụng mạnh mẽ, văn hóa doanh nghiệp tích cực.</li>
                        <li><strong>Đãi ngộ cạnh tranh & linh hoạt:</strong> Cập nhật thang bảng lương, áp dụng mô hình làm việc hybrid/remote.</li>
                        <li><strong>Đầu tư vào đào tạo:</strong> Nâng cao kỹ năng số, kỹ năng mềm và chuyên môn cho nhân viên.</li>
                        <li><strong>Thích ứng với Thế hệ Z:</strong> Tạo môi trường làm việc có mục đích, hỗ trợ sức khỏe tinh thần.</li>
                        <li><strong>Chú trọng Phát triển Bền vững (CSR):</strong> Nâng cao uy tín và sức hấp dẫn của doanh nghiệp.</li>
                    </ul>`,
                'for-employee': `
                    <ul class="space-y-4 list-disc list-inside text-gray-700 fade-in">
                        <li><strong>Chủ động nâng cao kỹ năng:</strong> Tập trung vào kỹ năng số, ngoại ngữ và kỹ năng mềm.</li>
                        <li><strong>Xây dựng thương hiệu cá nhân:</strong> Tận dụng mạng xã hội nghề nghiệp như LinkedIn.</li>
                        <li><strong>Tìm hiểu kỹ doanh nghiệp:</strong> Đánh giá văn hóa, giá trị và cơ hội phát triển trước khi ứng tuyển.</li>
                        <li><strong>Linh hoạt và thích ứng:</strong> Sẵn sàng học hỏi, đối mặt với thay đổi công nghệ và phương thức làm việc.</li>
                        <li><strong>Quan tâm sức khỏe tinh thần:</strong> Duy trì cân bằng giữa công việc và cuộc sống để phát triển bền vững.</li>
                    </ul>`
            };

            const ctxLabor = document.getElementById('laborForceChart').getContext('2d');
            new Chart(ctxLabor, {
                type: 'bar',
                data: {
                    labels: laborData.labels,
                    datasets: [{
                        label: 'Lực lượng lao động (triệu người)',
                        data: laborData.force,
                        backgroundColor: 'rgba(74, 144, 138, 0.6)',
                        borderColor: '#4A908A',
                        borderWidth: 1,
                        yAxisID: 'y'
                    }, {
                        label: 'Lao động có việc làm (triệu người)',
                        data: laborData.employed,
                        backgroundColor: 'rgba(208, 160, 76, 0.6)',
                        borderColor: '#D0A04C',
                        borderWidth: 1,
                        yAxisID: 'y'
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        title: { display: true, text: 'Quy Mô Lao Động và Việc Làm (Triệu Người)', font: {size: 16}},
                        tooltip: { mode: 'index', intersect: false }
                    },
                    scales: {
                        y: {
                            beginAtZero: false,
                            min: 51,
                            title: { display: true, text: 'Triệu Người' }
                        }
                    }
                }
            });

            const ctxUnemployment = document.getElementById('unemploymentChart').getContext('2d');
            const unemploymentChart = new Chart(ctxUnemployment, {
                type: 'bar',
                data: {
                    labels: unemploymentData.general.labels,
                    datasets: [{
                        label: 'Tỷ lệ thất nghiệp (%)',
                        data: unemploymentData.general.values,
                        backgroundColor: ['#4A908A', '#5EAAA8', '#A2D5C6'],
                        borderColor: '#333333',
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    indexAxis: 'y',
                    plugins: {
                        title: { display: true, text: 'Tỷ Lệ Thất Nghiệp (%) - Q1/2025', font: {size: 16} },
                        legend: { display: false }
                    },
                    scales: {
                        x: {
                            beginAtZero: true,
                            title: { display: true, text: 'Tỷ lệ (%)' }
                        }
                    }
                }
            });

            const ctxFdi = document.getElementById('fdiChart').getContext('2d');
            new Chart(ctxFdi, {
                type: 'line',
                data: {
                    labels: fdiData.labels,
                    datasets: [{
                        label: 'Vốn FDI đăng ký (tỷ USD)',
                        data: fdiData.values,
                        fill: true,
                        backgroundColor: 'rgba(74, 144, 138, 0.2)',
                        borderColor: '#4A908A',
                        tension: 0.1
                    }]
                },
                 options: {
                    responsive: true,
                    maintainAspectRatio: false,
                     plugins: {
                        legend: { display: false }
                    },
                    scales: {
                        y: {
                            beginAtZero: false,
                            title: { display: true, text: 'Tỷ USD' }
                        }
                    }
                }
            });

            function updateUnemploymentChart(type) {
                const data = unemploymentData[type];
                unemploymentChart.data.labels = data.labels;
                unemploymentChart.data.datasets[0].data = data.values;
                if(type === 'youth') {
                    unemploymentChart.data.datasets[0].backgroundColor = ['#D0A04C', '#E5B870', '#F3D59A'];
                } else {
                     unemploymentChart.data.datasets[0].backgroundColor = ['#4A908A', '#5EAAA8', '#A2D5C6'];
                }
                unemploymentChart.update();
            }

            document.getElementById('btnGeneralUnemployment').addEventListener('click', (e) => {
                updateUnemploymentChart('general');
                e.target.classList.add('active');
                document.getElementById('btnYouthUnemployment').classList.remove('active');
            });

            document.getElementById('btnYouthUnemployment').addEventListener('click', (e) => {
                updateUnemploymentChart('youth');
                e.target.classList.add('active');
                document.getElementById('btnGeneralUnemployment').classList.remove('active');
            });
            
            const jobTrendsContainer = document.getElementById('jobTrendsContainer');
            jobTrendsData.forEach((job, index) => {
                const card = document.createElement('div');
                card.className = 'job-card bg-white p-4 rounded-xl shadow-lg border border-transparent hover:border-gray-300';
                card.style.animationDelay = `${index * 0.1}s`;
                card.innerHTML = `
                    <div class="flex items-center mb-3">
                        <div class="text-3xl mr-4">${job.icon}</div>
                        <div>
                            <h5 class="font-bold text-lg text-[#333333]">${job.title}</h5>
                             <p class="text-xs text-gray-500">Nhấp để xem kỹ năng</p>
                        </div>
                    </div>
                    <div class="job-skills hidden mt-3 pl-2 border-l-2 border-[#4A908A]">
                        <ul class="text-sm text-gray-700 space-y-1">
                           ${job.skills.map(skill => `<li>- ${skill}</li>`).join('')}
                        </ul>
                    </div>
                `;
                jobTrendsContainer.appendChild(card);

                card.addEventListener('click', () => {
                    card.querySelector('.job-skills').classList.toggle('hidden');
                });
            });

            const tabContainer = document.getElementById('tab-content');
            const tabButtons = document.querySelectorAll('.tab-button');
            function updateTabContent(tabId) {
                tabContainer.innerHTML = recommendationsData[tabId];
                tabButtons.forEach(button => {
                    if (button.dataset.tab === tabId) {
                        button.classList.add('active');
                    } else {
                        button.classList.remove('active');
                    }
                });
            }
            tabButtons.forEach(button => {
                button.addEventListener('click', () => updateTabContent(button.dataset.tab));
            });
            updateTabContent('for-business');


            const navLinks = document.querySelectorAll('a[href^="#"]');
            navLinks.forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            const mobileNav = document.getElementById('mobile-nav');
            mobileNav.addEventListener('change', (e) => {
                 document.querySelector(e.target.value).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>

</body>
</html>
