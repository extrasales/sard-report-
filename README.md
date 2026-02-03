<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تقرير نتائج التسويق الرقمي - الصرد</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        'cairo': ['Cairo', 'sans-serif'],
                    },
                    colors: {
                        primary: '#1e40af',
                        secondary: '#3b82f6',
                        accent: '#f59e0b',
                        dark: '#0f172a',
                        'dark-light': '#1e293b',
                    },
                    animation: {
                        'fade-in-up': 'fadeInUp 0.8s ease-out',
                        'slide-in-right': 'slideInRight 0.6s ease-out',
                        'count-up': 'countUp 2s ease-out',
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'float': 'float 6s ease-in-out infinite',
                    },
                    keyframes: {
                        fadeInUp: {
                            '0%': { opacity: '0', transform: 'translateY(30px)' },
                            '100%': { opacity: '1', transform: 'translateY(0)' },
                        },
                        slideInRight: {
                            '0%': { opacity: '0', transform: 'translateX(-30px)' },
                            '100%': { opacity: '1', transform: 'translateX(0)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-20px)' },
                        }
                    }
                }
            }
        }
    </script>
    
    <style>
        body {
            font-family: 'Cairo', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            overflow-x: hidden;
        }
        
        .glass-card {
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .gradient-text {
            background: linear-gradient(135deg, #60a5fa 0%, #3b82f6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .metric-card {
            transition: all 0.3s ease;
        }
        
        .metric-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(59, 130, 246, 0.3);
        }
        
        .progress-bar {
            position: relative;
            overflow: hidden;
        }
        
        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            width: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .chart-container {
            position: relative;
            height: 300px;
        }
        
        .floating-shape {
            position: absolute;
            border-radius: 50%;
            opacity: 0.1;
            pointer-events: none;
        }
    </style>
</head>
<body class="text-white min-h-screen">

    <!-- Floating Background Shapes -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
        <div class="floating-shape w-96 h-96 bg-blue-500 top-0 right-0 blur-3xl animate-float"></div>
        <div class="floating-shape w-64 h-64 bg-purple-500 bottom-0 left-0 blur-3xl animate-float" style="animation-delay: 2s;"></div>
        <div class="floating-shape w-80 h-80 bg-cyan-500 top-1/2 left-1/2 blur-3xl animate-float" style="animation-delay: 4s;"></div>
    </div>

    <!-- Header -->
    <header class="relative z-10 pt-12 pb-8 px-6 text-center animate-fade-in-up">
        <div class="max-w-6xl mx-auto">
            <div class="inline-block mb-4 px-6 py-2 rounded-full bg-blue-500/20 border border-blue-400/30 text-blue-300 text-sm font-semibold tracking-wider">
                <i class="fas fa-calendar-alt ml-2"></i>
                يناير 2026
            </div>
            <h1 class="text-5xl md:text-7xl font-bold mb-4 gradient-text">الصرد</h1>
            <p class="text-xl md:text-2xl text-gray-400 font-light">تقرير نتائج التسويق الرقمي</p>
            <div class="mt-6 inline-flex items-center gap-2 text-gray-300 bg-white/5 px-6 py-3 rounded-2xl border border-white/10">
                <i class="fas fa-clock text-blue-400"></i>
                <span class="font-semibold">الفترة من 1 يناير - 31 يناير 2026</span>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="relative z-10 max-w-7xl mx-auto px-6 pb-20 space-y-8">

        <!-- Google Ads Section -->
        <section class="animate-fade-in-up" style="animation-delay: 0.2s;">
            <div class="glass-card rounded-3xl p-8 md:p-12">
                <div class="flex items-center gap-4 mb-8">
                    <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-blue-500 to-blue-700 flex items-center justify-center text-3xl shadow-lg shadow-blue-500/30">
                        <i class="fab fa-google"></i>
                    </div>
                    <div>
                        <h2 class="text-3xl font-bold text-white">جوجل أدز</h2>
                        <p class="text-gray-400">نتائج الحملات الإعلانية على Google</p>
                    </div>
                </div>

                <!-- Key Metrics Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
                    <!-- Total Spend -->
                    <div class="metric-card glass-card rounded-2xl p-6 border-l-4 border-blue-500">
                        <div class="flex justify-between items-start mb-4">
                            <div class="text-gray-400 text-sm">إجمالي التصرف</div>
                            <i class="fas fa-dollar-sign text-blue-400 text-xl"></i>
                        </div>
                        <div class="text-3xl font-bold text-white counter" data-target="1230">$1,230</div>
                        <div class="mt-2 text-xs text-green-400 flex items-center gap-1">
                            <i class="fas fa-arrow-up"></i>
                            <span>+12% عن الشهر الماضي</span>
                        </div>
                    </div>

                    <!-- Install Cost - UPDATED -->
                    <div class="metric-card glass-card rounded-2xl p-6 border-l-4 border-green-500 bg-gradient-to-br from-green-500/10 to-transparent">
                        <div class="flex justify-between items-start mb-4">
                            <div class="text-gray-400 text-sm">تكلفة التثبيت</div>
                            <i class="fas fa-mobile-alt text-green-400 text-xl"></i>
                        </div>
                        <div class="text-3xl font-bold text-white">$700</div>
                        <div class="mt-2 text-xs text-green-400 flex items-center gap-1">
                            <i class="fas fa-check-circle"></i>
                            <span>تم تحقيق الهدف</span>
                        </div>
                    </div>

                    <!-- Conversions -->
                    <div class="metric-card glass-card rounded-2xl p-6 border-l-4 border-purple-500">
                        <div class="flex justify-between items-start mb-4">
                            <div class="text-gray-400 text-sm">التحويلات</div>
                            <i class="fas fa-chart-line text-purple-400 text-xl"></i>
                        </div>
                        <div class="text-3xl font-bold text-white counter" data-target="8470">8,470</div>
                        <div class="mt-2 w-full bg-gray-700 rounded-full h-2">
                            <div class="bg-purple-500 h-2 rounded-full progress-bar" style="width: 85%"></div>
                        </div>
                    </div>

                    <!-- Installations -->
                    <div class="metric-card glass-card rounded-2xl p-6 border-l-4 border-orange-500">
                        <div class="flex justify-between items-start mb-4">
                            <div class="text-gray-400 text-sm">عدد التثبيتات</div>
                            <i class="fas fa-download text-orange-400 text-xl"></i>
                        </div>
                        <div class="text-3xl font-bold text-white counter" data-target="8350">8,350</div>
                        <div class="mt-2 text-xs text-orange-300">معدل تثبيت ممتاز</div>
                    </div>
                </div>

                <!-- Detailed Stats -->
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <!-- Left Column -->
                    <div class="space-y-6">
                        <h3 class="text-xl font-bold text-white mb-4 flex items-center gap-2">
                            <i class="fas fa-search text-blue-400"></i>
                            إعلانات البحث
                        </h3>
                        
                        <div class="space-y-4">
                            <div class="flex justify-between items-center p-4 rounded-xl bg-white/5 hover:bg-white/10 transition-colors">
                                <span class="text-gray-300">مشاهدات الفيديو</span>
                                <span class="text-2xl font-bold text-blue-400">50,600</span>
                            </div>
                            <div class="flex justify-between items-center p-4 rounded-xl bg-white/5 hover:bg-white/10 transition-colors">
                                <span class="text-gray-300">الظهور</span>
                                <span class="text-2xl font-bold text-white">106,032</span>
                            </div>
                            <div class="flex justify-between items-center p-4 rounded-xl bg-white/5 hover:bg-white/10 transition-colors">
                                <span class="text-gray-300">النقرات</span>
                                <span class="text-2xl font-bold text-white">2,694</span>
                            </div>
                            <div class="flex justify-between items-center p-4 rounded-xl bg-white/5 hover:bg-white/10 transition-colors">
                                <span class="text-gray-300">معدل النقر (CTR)</span>
                                <span class="text-2xl font-bold text-green-400">2.23%</span>
                            </div>
                        </div>
                    </div>

                    <!-- Right Column - Chart -->
                    <div class="glass-card rounded-2xl p-6">
                        <h3 class="text-xl font-bold text-white mb-4">توزيع الميزانية</h3>
                        <div class="chart-container">
                            <canvas id="budgetChart"></canvas>
                        </div>
                        <div class="mt-4 text-center">
                            <span class="text-3xl font-bold text-white">$8,760</span>
                            <p class="text-gray-400 text-sm">إجمالي الميزانية المخصصة</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SEO Section -->
        <section class="animate-fade-in-up" style="animation-delay: 0.4s;">
            <div class="glass-card rounded-3xl p-8 md:p-12">
                <div class="flex items-center gap-4 mb-8">
                    <div class="w-16 h-16 rounded-2xl bg-gradient-to-br from-green-500 to-emerald-700 flex items-center justify-center text-3xl shadow-lg shadow-green-500/30">
                        <i class="fas fa-search-dollar"></i>
                    </div>
                    <div>
                        <h2 class="text-3xl font-bold text-white">السيو SEO</h2>
                        <p class="text-gray-400">تحليل وتحسين محركات البحث - آخر 3 أشهر</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                    <!-- Stats Cards -->
                    <div class="lg:col-span-1 space-y-6">
                        <div class="glass-card rounded-2xl p-6 text-center border-t-4 border-green-500">
                            <div class="text-gray-400 mb-2">إجمالي الزيارات</div>
                            <div class="text-4xl font-bold text-white mb-2 counter" data-target="12540">12,540</div>
                            <div class="text-green-400 text-sm flex items-center justify-center gap-1">
                                <i class="fas fa-arrow-up"></i>
                                <span>+34% من الشهر الماضي</span>
                            </div>
                        </div>

                        <div class="glass-card rounded-2xl p-6 border-t-4 border-blue-500">
                            <div class="text-gray-400 mb-2">البلد الأكثر زيارة</div>
                            <div class="text-2xl font-bold text-white mb-1">العراق</div>
                            <div class="text-blue-400 text-sm">85% من إجمالي الزيارات</div>
                        </div>

                        <div class="glass-card rounded-2xl p-6 border-t-4 border-purple-500">
                            <div class="text-gray-400 mb-2">نسبة الموبايل</div>
                            <div class="text-2xl font-bold text-white mb-1">75%</div>
                            <div class="text-purple-400 text-sm">معظم الزيارات من الموبايل</div>
                        </div>
                    </div>

                    <!-- Charts -->
                    <div class="lg:col-span-2 space-y-6">
                        <div class="glass-card rounded-2xl p-6">
                            <h3 class="text-lg font-bold text-white mb-4">توزيع الزيارات حسب الدول</h3>
                            <div class="chart-container" style="height: 250px;">
                                <canvas id="countriesChart"></canvas>
                            </div>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div class="glass-card rounded-2xl p-6">
                                <h3 class="text-lg font-bold text-white mb-4 flex items-center gap-2">
                                    <i class="fas fa-tasks text-green-400"></i>
                                    مهام On Page SEO
                                </h3>
                                <ul class="space-y-3">
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-green-500 mt-1"></i>
                                        <span>تحديث وتحسين محتوى 80 منتج من منتجات Milwaukee</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-green-500 mt-1"></i>
                                        <span>إضافة Schema Markup (FAQ)</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-green-500 mt-1"></i>
                                        <span>تحديث Meta Descriptions</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-green-500 mt-1"></i>
                                        <span>إصلاح أخطاء 404 (من 10% إلى 2%)</span>
                                    </li>
                                </ul>
                            </div>

                            <div class="glass-card rounded-2xl p-6">
                                <h3 class="text-lg font-bold text-white mb-4 flex items-center gap-2">
                                    <i class="fas fa-globe text-blue-400"></i>
                                    مهام Off Page SEO
                                </h3>
                                <ul class="space-y-3">
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-blue-500 mt-1"></i>
                                        <span>نشر باك لينكس على Quora, Reddit, Medium</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-blue-500 mt-1"></i>
                                        <span>إصلاح ملف robots.txt</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-blue-500 mt-1"></i>
                                        <span>تحديث Sitemap</span>
                                    </li>
                                    <li class="flex items-start gap-3 text-gray-300 text-sm">
                                        <i class="fas fa-check-circle text-blue-500 mt-1"></i>
                                        <span>بناء ثقة محركات البحث</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Summary Section -->
        <section class="animate-fade-in-up" style="animation-delay: 0.6s;">
            <div class="glass-card rounded-3xl p-8 md:p-12 bg-gradient-to-br from-blue-600/20 to-purple-600/20 border border-blue-400/30">
                <h2 class="text-3xl font-bold text-center mb-8 gradient-text">ملخص النتائج</h2>
                <p class="text-lg text-gray-300 text-center leading-relaxed max-w-4xl mx-auto">
                    حققنا نمواً ملحوظاً في جميع قنوات التسويق الرقمي خلال شهر يناير 2026، مع زيادة كبيرة في المتابعين والتفاعل على السوشيال ميديا، ونتائج ممتازة في حملات جوجل أدز، وتحسينات جوهرية في السيو.
                </p>
                
                <div class="mt-8 flex justify-center gap-4 flex-wrap">
                    <div class="px-6 py-3 rounded-full bg-green-500/20 border border-green-400/30 text-green-300 flex items-center gap-2">
                        <i class="fas fa-check-double"></i>
                        <span>أداء ممتاز</span>
                    </div>
                    <div class="px-6 py-3 rounded-full bg-blue-500/20 border border-blue-400/30 text-blue-300 flex items-center gap-2">
                        <i class="fas fa-chart-line"></i>
                        <span>نمو مستمر</span>
                    </div>
                    <div class="px-6 py-3 rounded-full bg-purple-500/20 border border-purple-400/30 text-purple-300 flex items-center gap-2">
                        <i class="fas fa-trophy"></i>
                        <span>تحقيق الأهداف</span>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="relative z-10 text-center py-8 text-gray-500 text-sm">
        <p>© 2026 تقرير التسويق الرقمي - الصرد | جميع الحقوق محفوظة</p>
    </footer>

    <script>
        // Initialize Charts
        document.addEventListener('DOMContentLoaded', function() {
            
            // Budget Distribution Chart
            const budgetCtx = document.getElementById('budgetChart').getContext('2d');
            new Chart(budgetCtx, {
                type: 'doughnut',
                data: {
                    labels: ['إعلانات البحث', 'إعلانات اليوتيوب', 'إعلانات التطبيقات', 'إعادة الاستهداف'],
                    datasets: [{
                        data: [45, 25, 20, 10],
                        backgroundColor: [
                            'rgba(59, 130, 246, 0.8)',
                            'rgba(239, 68, 68, 0.8)',
                            'rgba(16, 185, 129, 0.8)',
                            'rgba(245, 158, 11, 0.8)'
                        ],
                        borderColor: [
                            'rgba(59, 130, 246, 1)',
                            'rgba(239, 68, 68, 1)',
                            'rgba(16, 185, 129, 1)',
                            'rgba(245, 158, 11, 1)'
                        ],
                        borderWidth: 2
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                color: '#94a3b8',
                                font: { family: 'Cairo', size: 12 },
                                padding: 20
                            }
                        }
                    },
                    cutout: '70%'
                }
            });

            // Countries Chart
            const countriesCtx = document.getElementById('countriesChart').getContext('2d');
            new Chart(countriesCtx, {
                type: 'bar',
                data: {
                    labels: ['العراق', 'السعودية', 'الإمارات', 'مصر', 'الأردن'],
                    datasets: [{
                        label: 'عدد الزيارات',
                        data: [6000, 1500, 800, 600, 400],
                        backgroundColor: [
                            'rgba(59, 130, 246, 0.8)',
                            'rgba(16, 185, 129, 0.8)',
                            'rgba(245, 158, 11, 0.8)',
                            'rgba(239, 68, 68, 0.8)',
                            'rgba(139, 92, 246, 0.8)'
                        ],
                        borderColor: [
                            'rgba(59, 130, 246, 1)',
                            'rgba(16, 185, 129, 1)',
                            'rgba(245, 158, 11, 1)',
                            'rgba(239, 68, 68, 1)',
                            'rgba(139, 92, 246, 1)'
                        ],
                        borderWidth: 2,
                        borderRadius: 8
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
                            beginAtZero: true,
                            grid: { color: 'rgba(255, 255, 255, 0.1)' },
                            ticks: { color: '#94a3b8', font: { family: 'Cairo' } }
                        },
                        x: {
                            grid: { display: false },
                            ticks: { color: '#94a3b8', font: { family: 'Cairo' } }
                        }
                    }
                }
            });

            // Counter Animation
            const counters = document.querySelectorAll('.counter');
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-target'));
                const duration = 2000;
                const increment = target / (duration / 16);
                let current = 0;
                
                const updateCounter = () => {
                    current += increment;
                    if (current < target) {
                        counter.textContent = Math.floor(current).toLocaleString();
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target.toLocaleString();
                    }
                };
                
                // Start animation when element is in view
                const observer = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            updateCounter();
                            observer.unobserve(entry.target);
                        }
                    });
                });
                
                observer.observe(counter);
            });
        });
    </script>
</body>
</html>
