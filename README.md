<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Expensive — премиальный Minecraft клиент с мощной KillAura, удобным интерфейсом и облачными конфигами.">
    <title>Expensive — Premium Minecraft Client</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap">
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
       
        :root {
            --purple-400: #c084fc;
            --purple-500: #a855f7;
            --purple-600: #9333ea;
            --purple-900: #4c1d95;
        }

        body {
            font-family: 'Inter', system-ui, sans-serif;
            background: #0a0a0f;
            color: #e0e0ff;
            overflow-x: hidden;
        }

        #particles {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .hero-bg {
            background: linear-gradient(rgba(10,10,15,0.75), rgba(10,10,15,0.92)),
                        url('https://i.imgur.com/maxresdefault.jpg') center/cover no-repeat fixed;
        }

        .purple-btn {
            background: linear-gradient(90deg, #7c3aed, #c026d3);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .purple-btn:hover {
            transform: translateY(-4px) scale(1.03);
            box-shadow: 0 0 35px rgba(192, 38, 211, 0.7);
        }

        .card {
            background: rgba(17, 17, 24, 0.95);
            border: 1px solid #6b21a8;
            transition: all 0.4s;
        }
        .card:hover {
            transform: translateY(-8px);
            border-color: #c026d3;
        }

        .screenshot {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .screenshot:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(168, 85, 247, 0.5);
        }

        /* Scroll Animations */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.25, 0.1, 0.25, 1);
        }

        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .animate-on-scroll.delay-100 { transition-delay: 100ms; }
        .animate-on-scroll.delay-200 { transition-delay: 200ms; }
        .animate-on-scroll.delay-300 { transition-delay: 300ms; }

        .modal {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.97);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <canvas id="particles"></canvas>

    <!-- Header -->
    <header class="sticky top-0 z-50 bg-[#0a0a0f]/95 backdrop-blur-lg border-b border-purple-900">
        <div class="max-w-7xl mx-auto px-8 py-5 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <span class="text-4xl">💎</span>
                <h1 class="text-3xl font-bold tracking-tighter">Expensive</h1>
            </div>
            <nav class="hidden md:flex gap-8 text-lg font-medium">
                <a href="#features" class="hover:text-purple-400 transition-colors">Функции</a>
                <a href="#gameplay" class="hover:text-purple-400 transition-colors">Геймплей</a>
                <a href="#screenshots" class="hover:text-purple-400 transition-colors">Скриншоты</a>
                <a href="#pricing" class="hover:text-purple-400 transition-colors">Купить</a>
            </nav>
            <button onclick="document.getElementById('pricing').scrollIntoView({behavior: 'smooth'})"
                    class="px-8 py-3 bg-white/10 hover:bg-white/20 rounded-2xl transition-all font-semibold">
                Купить
            </button>
        </div>
    </header>

    <!-- Hero -->
    <section class="hero-bg h-screen flex items-center text-center relative">
        <div class="max-w-5xl mx-auto px-6 z-10">
            <h1 class="text-6xl md:text-7xl font-bold mb-6 leading-tight tracking-tighter animate-on-scroll visible">
                Expensive — простой путь<br>к победе
            </h1>
            <p class="text-xl md:text-2xl max-w-2xl mx-auto mb-10 text-purple-100 animate-on-scroll visible delay-200">
                Мощный клиент, который позволяет доминировать на любом сервере Minecraft
            </p>
            <div class="flex flex-col sm:flex-row justify-center gap-6 animate-on-scroll visible delay-300">
                <button onclick="document.getElementById('pricing').scrollIntoView({behavior: 'smooth'})"
                        class="purple-btn px-12 py-6 rounded-3xl text-2xl font-semibold inline-flex items-center gap-3 shadow-xl">
                    Купить продукт →
                </button>
                <button onclick="document.getElementById('gameplay').scrollIntoView({behavior: 'smooth'})"
                        class="px-12 py-6 border-2 border-purple-500 hover:bg-purple-900/40 rounded-3xl text-xl font-medium">
                    Смотреть геймплей
                </button>
            </div>
        </div>
    </section>

    <!-- Video -->
    <section id="gameplay" class="py-20 bg-[#111118]">
        <div class="max-w-6xl mx-auto px-6">
            <h2 class="text-4xl font-bold text-center mb-12 animate-on-scroll">Геймплей Expensive</h2>
            <div class="aspect-video w-full max-w-5xl mx-auto rounded-3xl overflow-hidden border-2 border-purple-700 shadow-2xl animate-on-scroll">
                <iframe src="https://www.youtube.com/embed/0VCZcdbL3YA" 
                        frameborder="0" allowfullscreen class="w-full h-full"></iframe>
            </div>
        </div>
    </section>

    <!-- Screenshots -->
    <section id="screenshots" class="py-20 bg-[#0a0a0f]">
        <div class="max-w-7xl mx-auto px-6">
            <h2 class="text-4xl font-bold text-center mb-12 animate-on-scroll">Интерфейс Expensive</h2>
            <div class="grid md:grid-cols-2 gap-10">
                <img src="https://i.imgur.com/3RxPx.png" 
                     onclick="openModal(this)" 
                     alt="Expensive Client UI"
                     class="screenshot w-full rounded-3xl shadow-xl cursor-pointer animate-on-scroll slide-up">
                <img src="https://i.imgur.com/maxresdefault.jpg" 
                     onclick="openModal(this)" 
                     alt="Expensive Menu"
                     class="screenshot w-full rounded-3xl shadow-xl cursor-pointer animate-on-scroll slide-up delay-200">
            </div>
        </div>
    </section>

    <!-- Modal -->
    <div id="imageModal" class="modal">
        <div class="modal-content relative max-w-[95%] max-h-[95%] p-4">
            <span class="close absolute -top-12 right-4 text-5xl text-white cursor-pointer hover:text-purple-400 transition-colors" onclick="closeModal()">×</span>
            <img id="modalImage" src="" alt="" class="rounded-2xl border-4 border-purple-500 shadow-2xl w-full">
        </div>
    </div>

    <!-- Features -->
    <section id="features" class="py-20 bg-[#111118
