<!DOCTYPE html>
<html lang="en" class="scroll-smooth dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manas Balkrishna Ippar | Portfolio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Space Grotesk', 'monospace'],
                    },
                    colors: {
                        darkBg: '#070709',
                        charcoal: '#0e0f14',
                        cardBg: 'rgba(16, 17, 24, 0.8)',
                        crimsonRed: '#dc2626',
                        crimsonDark: '#991b1b',
                    },
                    boxShadow: {
                        'neon-crimson': '0 0 35px -5px rgba(220, 38, 38, 0.4)',
                        'glass': '0 8px 32px 0 rgba(0, 0, 0, 0.4)',
                    }
                }
            }
        }
    </script>
    <style>
        :root {
            --bg-color: #070709;
            --surface-color: #0e0f14;
            --border-color: rgba(255, 255, 255, 0.08);
            --accent-crimson: #dc2626;
            --accent-crimson-glow: rgba(220, 38, 38, 0.4);
        }

        body {
            background-color: var(--bg-color);
            color: #f3f4f6;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        /* Subtle animated background grid & cyber blobs */
        .bg-grid {
            background-size: 40px 40px;
            background-image: 
                linear-gradient(to right, rgba(255, 255, 255, 0.02) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
        }

        .blob-1 {
            position: absolute;
            top: 5%;
            left: 10%;
            width: 500px;
            height: 500px;
            background: rgba(220, 38, 38, 0.09);
            filter: blur(140px);
            border-radius: 50%;
            z-index: -1;
            animation: pulse-slow 12s infinite alternate;
        }

        .blob-2 {
            position: absolute;
            top: 55%;
            right: 5%;
            width: 550px;
            height: 550px;
            background: rgba(153, 27, 27, 0.08);
            filter: blur(150px);
            border-radius: 50%;
            z-index: -1;
            animation: pulse-slow 15s infinite alternate-reverse;
        }

        @keyframes pulse-slow {
            0% { transform: scale(1) translate(0, 0); }
            100% { transform: scale(1.12) translate(30px, 40px); }
        }

        /* Glassmorphism styling */
        .glass-card {
            background: rgba(14, 15, 20, 0.78);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid var(--border-color);
        }

        .glass-card:hover {
            border-color: rgba(220, 38, 38, 0.45);
            box-shadow: 0 12px 35px -10px rgba(220, 38, 38, 0.25);
        }

        .glass-nav {
            background: rgba(7, 7, 9, 0.92);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
        }

        /* Glowing border animation for profile photo */
        @keyframes rotate-glow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .animated-border-container {
            position: relative;
            border-radius: 50%;
            overflow: hidden;
            padding: 4px;
        }

        .animated-border-container::before {
            content: '';
            position: absolute;
            inset: -50%;
            background: conic-gradient(from 0deg, #dc2626, #7f1d1d, #ef4444, #dc2626);
            animation: rotate-glow 7s linear infinite;
            z-index: 0;
        }

        .profile-img-inner {
            position: relative;
            z-index: 1;
            border-radius: 50%;
            overflow: hidden;
            background: #0e0f14;
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #070709;
        }
        ::-webkit-scrollbar-thumb {
            background: #27272a;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #dc2626;
        }

        .profile-img-inner img {
            object-position: center top;
        }

        .hero-profile-ring {
            transform: translateZ(0);
        }

        @media (max-width: 640px) {
            .hero-profile-ring {
                transform: scale(0.92);
            }
        }

        .reveal-ready {
            opacity: 0;
            transform: translateY(18px);
            transition: opacity .7s ease, transform .7s ease;
        }
        .reveal-visible { opacity: 1; transform: translateY(0); }
        .click-ripple {
            position: absolute;
            width: 12px;
            height: 12px;
            border-radius: 9999px;
            background: rgba(255,255,255,.28);
            transform: translate(-50%, -50%) scale(1);
            animation: ripple .5s ease-out forwards;
            pointer-events: none;
        }
        button, a { position: relative; overflow: hidden; }
        button:focus-visible, a:focus-visible, input:focus-visible, textarea:focus-visible {
            outline: 2px solid rgba(239,68,68,.8);
            outline-offset: 3px;
        }
        @keyframes ripple { to { transform: translate(-50%, -50%) scale(14); opacity: 0; } }
        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after { scroll-behavior: auto !important; animation-duration: .01ms !important; transition-duration: .01ms !important; }
            .reveal-ready { opacity: 1; transform: none; }
        }
    
        html { scroll-padding-top: 92px; }
        .scroll-progress{position:fixed;top:0;left:0;width:0%;height:3px;z-index:100;background:linear-gradient(90deg,#dc2626,#fb7185,#ef4444);box-shadow:0 0 14px rgba(220,38,38,.65)}
        .cursor-glow{position:fixed;width:220px;height:220px;border-radius:999px;pointer-events:none;z-index:0;transform:translate(-50%,-50%);background:radial-gradient(circle,rgba(220,38,38,.10),transparent 68%)}
        .premium-card{transition:transform .35s cubic-bezier(.2,.8,.2,1),border-color .35s ease,box-shadow .35s ease;transform-style:preserve-3d}
        .premium-card:hover{transform:translateY(-7px);border-color:rgba(220,38,38,.45)!important;box-shadow:0 24px 70px rgba(0,0,0,.30),0 0 28px rgba(220,38,38,.08)}
        .reveal{opacity:0;transform:translateY(26px);transition:opacity .7s ease,transform .7s cubic-bezier(.2,.8,.2,1)}
        .reveal.is-visible{opacity:1;transform:translateY(0)}
        .skill-chip{transition:transform .2s ease,border-color .2s ease,background .2s ease}
        .skill-chip:hover{transform:translateY(-2px) scale(1.02);border-color:rgba(220,38,38,.5);background:rgba(220,38,38,.08)}
        .toast{position:fixed;right:24px;bottom:24px;z-index:90;max-width:min(390px,calc(100vw - 32px));padding:14px 16px;border:1px solid rgba(255,255,255,.12);border-radius:16px;background:rgba(14,15,20,.92);backdrop-filter:blur(18px);box-shadow:0 18px 55px rgba(0,0,0,.38);color:#e5e7eb;transform:translateY(20px);opacity:0;pointer-events:none;transition:.3s ease}
        .toast.show{opacity:1;transform:translateY(0)}
        .back-top{position:fixed;right:22px;bottom:22px;z-index:80;width:48px;height:48px;border-radius:14px;display:grid;place-items:center;background:rgba(14,15,20,.86);border:1px solid rgba(255,255,255,.12);color:#fff;opacity:0;transform:translateY(15px);pointer-events:none;transition:.3s ease}
        .back-top.show{opacity:1;transform:translateY(0);pointer-events:auto}
        .back-top:hover{border-color:rgba(220,38,38,.55);color:#f87171}
        .availability-dot{box-shadow:0 0 0 0 rgba(34,197,94,.55);animation:availabilityPulse 2s infinite}
        @keyframes availabilityPulse{0%{box-shadow:0 0 0 0 rgba(34,197,94,.5)}70%{box-shadow:0 0 0 9px rgba(34,197,94,0)}100%{box-shadow:0 0 0 0 rgba(34,197,94,0)}}
        .typing-caret{display:inline-block;width:2px;height:1em;background:#ef4444;margin-left:5px;vertical-align:-.12em;animation:caretBlink 1s steps(1) infinite}
        @keyframes caretBlink{50%{opacity:0}}
        .copy-btn{opacity:0;transition:opacity .2s ease}
        .contact-copy:hover .copy-btn,.contact-copy:focus-within .copy-btn{opacity:1}
        @media(max-width:640px){.cursor-glow{display:none}.toast{right:16px;bottom:16px}.back-top{right:16px;bottom:16px}.copy-btn{opacity:1}}
        @media(prefers-reduced-motion:reduce){*,*::before,*::after{scroll-behavior:auto!important;animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important}.reveal{opacity:1;transform:none}.cursor-glow{display:none}}

    </style>

<style id="clean-premium-ui">
/* =========================================================
   CLEAN PREMIUM PORTFOLIO OVERRIDE
   Keeps the existing content/functionality while refreshing
   the visual language.
   ========================================================= */

:root{
  --clean-bg:#f7f8fc;
  --clean-surface:rgba(255,255,255,.86);
  --clean-surface-solid:#ffffff;
  --clean-text:#111827;
  --clean-muted:#667085;
  --clean-border:#e7e9ef;
  --clean-accent:#e11d48;
  --clean-accent-2:#be123c;
  --clean-shadow:0 18px 55px rgba(15,23,42,.08);
  --clean-shadow-hover:0 24px 70px rgba(15,23,42,.13);
}

/* Page */
html{scroll-behavior:smooth;background:var(--clean-bg)!important;}
body{
  background:
    radial-gradient(circle at 8% 8%, rgba(225,29,72,.055), transparent 28%),
    radial-gradient(circle at 92% 24%, rgba(99,102,241,.045), transparent 25%),
    var(--clean-bg)!important;
  color:var(--clean-text)!important;
  font-family:'Inter',sans-serif!important;
}
.bg-grid{
  background-image:
    linear-gradient(rgba(15,23,42,.025) 1px,transparent 1px),
    linear-gradient(90deg,rgba(15,23,42,.025) 1px,transparent 1px)!important;
  background-size:42px 42px!important;
}

/* Remove visual noise */
.blob-1,.blob-2{opacity:.35!important;filter:blur(130px)!important;}
.cursor-glow{display:none!important;}
#scroll-progress{background:linear-gradient(90deg,#e11d48,#fb7185)!important;box-shadow:none!important;height:2px!important;}
.toast{
  background:rgba(17,24,39,.94)!important;
  border:1px solid rgba(255,255,255,.12)!important;
  box-shadow:0 20px 50px rgba(15,23,42,.2)!important;
}

/* Navigation */
header.glass-nav{
  background:rgba(255,255,255,.86)!important;
  border-bottom:1px solid rgba(15,23,42,.07)!important;
  box-shadow:0 8px 30px rgba(15,23,42,.045)!important;
  backdrop-filter:blur(20px)!important;
  -webkit-backdrop-filter:blur(20px)!important;
}
header.glass-nav > div{
  height:74px!important;
}
header.glass-nav a.font-mono{
  color:#111827!important;
  letter-spacing:-.02em!important;
}
header.glass-nav a.font-mono .text-red-600,
header.glass-nav a.font-mono .text-red-500{
  color:var(--clean-accent)!important;
}
header.glass-nav nav a{
  color:#667085!important;
  transition:color .2s ease,transform .2s ease!important;
}
header.glass-nav nav a:hover{
  color:#111827!important;
  transform:translateY(-1px);
}
header.glass-nav .bg-red-500\/10{
  background:rgba(225,29,72,.07)!important;
  border-color:rgba(225,29,72,.15)!important;
  color:#be123c!important;
}
header.glass-nav .bg-red-500{
  background:#e11d48!important;
}

/* Mobile nav */
#mobile-menu{
  background:rgba(255,255,255,.96)!important;
  border-color:#e7e9ef!important;
}
#mobile-menu a{color:#475467!important;}
#mobile-menu a:hover{color:#e11d48!important;}

/* Sections */
section{
  position:relative;
}
#home{
  min-height:calc(100vh - 10px)!important;
  padding-top:112px!important;
}
#about,#skills,#project,#contact{
  padding-top:112px!important;
  padding-bottom:112px!important;
}

/* Hero */
#home .inline-flex{
  background:rgba(225,29,72,.07)!important;
  border:1px solid rgba(225,29,72,.15)!important;
  color:#be123c!important;
  border-radius:999px!important;
  padding:8px 13px!important;
  font-size:11px!important;
  letter-spacing:.05em!important;
}
#home h1{
  color:#111827!important;
  font-family:'Space Grotesk',sans-serif!important;
  letter-spacing:-.055em!important;
  line-height:.98!important;
}
#home h1 .text-transparent{
  background-image:linear-gradient(90deg,#e11d48,#be123c)!important;
}
#home h2{
  color:#344054!important;
  font-family:'Space Grotesk',sans-serif!important;
  letter-spacing:-.045em!important;
  line-height:1.08!important;
}
#home p{
  color:#667085!important;
  max-width:680px!important;
  line-height:1.8!important;
}
#home .flex.flex-wrap.gap-4.pt-2 a:first-child{
  background:#111827!important;
  color:#fff!important;
  box-shadow:0 12px 28px rgba(17,24,39,.16)!important;
  border-radius:13px!important;
}
#home .flex.flex-wrap.gap-4.pt-2 a:first-child:hover{
  background:#1f2937!important;
  box-shadow:0 16px 34px rgba(17,24,39,.2)!important;
}
#home .flex.flex-wrap.gap-4.pt-2 a:last-child{
  background:#fff!important;
  color:#344054!important;
  border:1px solid #e4e7ec!important;
  box-shadow:0 8px 25px rgba(15,23,42,.05)!important;
  border-radius:13px!important;
}
#home .flex.flex-wrap.gap-4.pt-2 a:last-child:hover{
  border-color:#d0d5dd!important;
  color:#111827!important;
}
#home .flex.items-center.gap-6.pt-4 a{
  background:#fff!important;
  border:1px solid #e4e7ec!important;
  color:#667085!important;
  box-shadow:0 7px 20px rgba(15,23,42,.045)!important;
  border-radius:12px!important;
}
#home .flex.items-center.gap-6.pt-4 a:hover{
  color:#e11d48!important;
  border-color:rgba(225,29,72,.3)!important;
}

/* Profile image */
.animated-border-container{
  padding:5px!important;
  background:#fff!important;
  box-shadow:0 25px 70px rgba(15,23,42,.13)!important;
}
.animated-border-container::before{
  background:conic-gradient(from 0deg,#e11d48,#fda4af,#fb7185,#e11d48)!important;
  opacity:.9;
}
.profile-img-inner{
  background:#fff!important;
  border:5px solid #fff!important;
}
.profile-img-inner img{
  filter:saturate(.96) contrast(1.02)!important;
}
.hero-profile-ring{
  transform:translateZ(0)!important;
}

/* Cards / surfaces */
.glass-card,
.premium-card{
  background:var(--clean-surface)!important;
  border:1px solid var(--clean-border)!important;
  color:var(--clean-text)!important;
  box-shadow:var(--clean-shadow)!important;
  backdrop-filter:blur(16px)!important;
  -webkit-backdrop-filter:blur(16px)!important;
}
.glass-card:hover,
.premium-card:hover{
  border-color:#d9dde6!important;
  box-shadow:var(--clean-shadow-hover)!important;
  transform:translateY(-5px)!important;
}

/* Section headings */
#about h2,#skills h2,#project h2,#contact h2{
  color:#111827!important;
  font-family:'Space Grotesk',sans-serif!important;
  letter-spacing:-.045em!important;
}
#about h3,#skills h3,#project h3,#contact h3{
  color:#1f2937!important;
}
#about p,#skills p,#project p,#contact p{
  color:#667085!important;
}
#about .text-red-500,#skills .text-red-500,#project .text-red-500,#contact .text-red-500{
  color:#e11d48!important;
}
#about .text-gray-400,#skills .text-gray-400,#project .text-gray-400,#contact .text-gray-400{
  color:#667085!important;
}
#about .text-white,#skills .text-white,#project .text-white,#contact .text-white{
  color:#111827!important;
}
#about .text-gray-300,#skills .text-gray-300,#project .text-gray-300,#contact .text-gray-300{
  color:#475467!important;
}

/* Skill chips */
.skill-chip{
  background:#fff!important;
  border:1px solid #e4e7ec!important;
  color:#344054!important;
  box-shadow:0 6px 18px rgba(15,23,42,.04)!important;
}
.skill-chip:hover{
  background:#fff7f8!important;
  border-color:rgba(225,29,72,.28)!important;
  color:#be123c!important;
}

/* Accent badges / icons */
#about .bg-red-500\/10,#skills .bg-red-500\/10,#project .bg-red-500\/10,#contact .bg-red-500\/10{
  background:rgba(225,29,72,.07)!important;
  border-color:rgba(225,29,72,.12)!important;
}
#about .bg-red-500\/10 i,#skills .bg-red-500\/10 i,#project .bg-red-500\/10 i,#contact .bg-red-500\/10 i{
  color:#e11d48!important;
}

/* Forms */
#contact input,#contact textarea{
  background:#fff!important;
  color:#111827!important;
  border:1px solid #e4e7ec!important;
  box-shadow:0 4px 14px rgba(15,23,42,.025)!important;
}
#contact input::placeholder,#contact textarea::placeholder{
  color:#98a2b3!important;
}
#contact input:focus,#contact textarea:focus{
  border-color:rgba(225,29,72,.45)!important;
  box-shadow:0 0 0 4px rgba(225,29,72,.07)!important;
}
#contact button[type="submit"]{
  background:#111827!important;
  box-shadow:0 12px 28px rgba(17,24,39,.14)!important;
}
#contact button[type="submit"]:hover{
  background:#1f2937!important;
}

/* Links and project controls */
#project a,
#project button{
  border-radius:12px!important;
}
#project .text-red-400,#project .text-red-300{
  color:#be123c!important;
}

/* Decorative separators */
#about::before,#skills::before,#project::before,#contact::before{
  content:"";
  position:absolute;
  top:0;
  left:50%;
  width:min(1180px,calc(100% - 40px));
  height:1px;
  transform:translateX(-50%);
  background:linear-gradient(90deg,transparent,#e4e7ec,transparent);
}

/* Back-to-top */
.back-top{
  background:#111827!important;
  border:1px solid #1f2937!important;
  color:#fff!important;
  border-radius:14px!important;
  box-shadow:0 12px 28px rgba(15,23,42,.15)!important;
}
.back-top:hover{
  background:#1f2937!important;
  color:#fff!important;
}

/* Scrollbar */
::-webkit-scrollbar{width:7px!important;}
::-webkit-scrollbar-track{background:#f7f8fc!important;}
::-webkit-scrollbar-thumb{background:#cbd0d9!important;border-radius:99px!important;}
::-webkit-scrollbar-thumb:hover{background:#98a2b3!important;}

/* Footer */
footer{
  background:#111827!important;
  color:#d0d5dd!important;
  border-top:1px solid #1f2937!important;
}
footer .text-white{color:#fff!important;}
footer .text-gray-400{color:#98a2b3!important;}

/* Cleaner motion */
.reveal,.reveal-ready{
  transition:opacity .65s ease,transform .65s cubic-bezier(.2,.8,.2,1)!important;
}
@media (prefers-reduced-motion:reduce){
  *,*::before,*::after{
    animation-duration:.01ms!important;
    transition-duration:.01ms!important;
  }
}

/* Responsive */
@media(max-width:1024px){
  #home{padding-top:105px!important;}
  #about,#skills,#project,#contact{
    padding-top:90px!important;
    padding-bottom:90px!important;
  }
}
@media(max-width:640px){
  header.glass-nav > div{height:68px!important;}
  #home{
    min-height:auto!important;
    padding-top:105px!important;
    padding-bottom:70px!important;
  }
  #about,#skills,#project,#contact{
    padding-top:76px!important;
    padding-bottom:76px!important;
  }
  #home h1{
    font-size:3.35rem!important;
  }
  #home h2{
    font-size:2rem!important;
  }
  #home p{
    font-size:.96rem!important;
  }
  .glass-card,.premium-card{
    border-radius:20px!important;
  }
}
</style>

</head>
<body class="bg-grid relative min-h-screen">
    <div id="scroll-progress" class="scroll-progress" aria-hidden="true"></div>
    <div id="cursor-glow" class="cursor-glow" aria-hidden="true"></div>
    <div id="toast" class="toast" role="status" aria-live="polite"></div>

    <div id="scroll-progress" class="fixed top-0 left-0 h-1 bg-red-500 z-[100] w-0 shadow-[0_0_14px_rgba(239,68,68,.8)] transition-[width] duration-75"></div>
    <div class="blob-1"></div>
    <div class="blob-2"></div>

    <header class="fixed top-0 left-0 right-0 z-50 glass-nav transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <a href="#home" class="font-mono font-bold text-xl tracking-wider text-white flex items-center gap-2">
                <span class="text-red-600">&lt;</span>MANAS<span class="text-red-500">/</span>IPPAR<span class="text-red-600">&gt;</span>
            </a>

            <!-- Desktop Navigation Links -->
            <nav class="hidden md:flex items-center gap-8 font-medium text-sm text-gray-300">
                <a href="#home" class="hover:text-red-500 transition-colors">Home</a>
                <a href="#about" class="hover:text-red-500 transition-colors">About</a>
                <a href="#skills" class="hover:text-red-500 transition-colors">Skills</a>
                <a href="#project" class="hover:text-red-500 transition-colors">Project</a>
                <a href="#contact" class="hover:text-red-500 transition-colors">Contact</a>
            </nav>

            <!-- Status Indicator & Mobile Button -->
            <div class="flex items-center gap-4">
                <div class="hidden sm:flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-red-500/10 border border-red-500/20 text-xs text-red-300">
                    <span class="availability-dot w-2 h-2 rounded-full bg-red-500"></span>
                    <span>Available for Opportunities</span>
                </div>
                
                <button id="mobile-menu-btn" aria-label="Toggle mobile menu" aria-expanded="false" class="md:hidden text-gray-300 hover:text-white p-2">
                    <i class="fa-solid fa-bars text-xl"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden glass-card border-t border-white/10 px-6 py-4 flex flex-col gap-4">
            <a href="#home" class="mobile-link text-gray-300 hover:text-red-500 py-1 font-medium">Home</a>
            <a href="#about" class="mobile-link text-gray-300 hover:text-red-500 py-1 font-medium">About</a>
            <a href="#skills" class="mobile-link text-gray-300 hover:text-red-500 py-1 font-medium">Skills</a>
            <a href="#project" class="mobile-link text-gray-300 hover:text-red-500 py-1 font-medium">Project</a>
            <a href="#contact" class="mobile-link text-gray-300 hover:text-red-500 py-1 font-medium">Contact</a>
            <div class="pt-2 border-t border-white/10 flex items-center gap-2 text-xs text-red-300">
                <span class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></span>
                <span>Available for Opportunities</span>
            </div>
        </div>
    </header>

    <section id="home" class="min-h-screen pt-28 pb-16 flex items-center justify-center px-4 sm:px-6 lg:px-8 relative">
        <div class="max-w-7xl mx-auto w-full grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
            
            <!-- Hero Left Column -->
            <div class="lg:col-span-7 flex flex-col items-start gap-6 text-left">
                <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-red-500/10 border border-red-500/30 text-red-400 text-xs font-mono tracking-wide">
                    <i class="fa-solid fa-graduation-cap"></i>
                    <span>BCS GRADUATE • MCS (AI & DATA SCIENCE) • SOFTWARE DEVELOPMENT</span>
                </div>

                <div class="space-y-2">
                    <h1 class="text-5xl sm:text-7xl lg:text-8xl font-bold tracking-tight text-white font-mono">
                        Hi, I'm <span class="text-transparent bg-clip-text bg-gradient-to-r from-red-500 via-rose-500 to-red-600">Manas.</span>
                    </h1>
                    <h2 class="text-4xl sm:text-6xl lg:text-7xl font-bold tracking-tight text-gray-200">
                        I build digital experiences that solve real problems.
                    </h2>
                </div>

                <p class="text-gray-400 text-base sm:text-lg max-w-2xl leading-relaxed">
                    BCS graduate and current MCS (AI & Data Science) student with an interest in software development, web development, AI and Data Science. I enjoy learning new technologies and turning ideas into practical applications.
                </p>

                <div class="flex flex-wrap gap-4 pt-2">
                    <a href="#project" class="px-6 py-3.5 rounded-xl bg-red-600 hover:bg-red-500 text-white font-medium flex items-center gap-2 transition-all shadow-neon-crimson hover:scale-[1.02] active:scale-[0.98]">
                        <span>View My Project</span>
                        <i class="fa-solid fa-arrow-right text-sm"></i>
                    </a>
                    <a href="#contact" class="px-6 py-3.5 rounded-xl glass-card text-gray-200 hover:text-white font-medium flex items-center gap-2 transition-all hover:border-red-500/50 hover:scale-[1.02] active:scale-[0.98]">
                        <span>Let's Connect</span>
                        <i class="fa-regular fa-paper-plane text-sm"></i>
                    </a>
                </div>

                <div class="flex items-center gap-6 pt-4 text-gray-400 text-lg">
                    <a href="https://www.linkedin.com/in/manas-ippar-07b004329" target="_blank" rel="noopener noreferrer" class="hover:text-red-500 transition-colors p-2.5 rounded-lg glass-card" aria-label="LinkedIn">
                        <i class="fa-brands fa-linkedin-in"></i>
                    </a>
                    <a href="https://share.google/0Renry8I3rSxdHjFz" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors p-2.5 rounded-lg glass-card" aria-label="GitHub">
                        <i class="fa-brands fa-github"></i>
                    </a>
                    <a href="mailto:manasippar4@gmail.com" class="hover:text-red-400 transition-colors p-2.5 rounded-lg glass-card" aria-label="Email">
                        <i class="fa-solid fa-envelope"></i>
                    </a>
                </div>
            </div>

            <!-- Hero Right Column (Embedded Profile Photo & Floating Badges) -->
            <div class="lg:col-span-5 flex justify-center relative">
                <div class="relative w-80 h-80 sm:w-[28rem] sm:h-[28rem] lg:w-[31rem] lg:h-[31rem] flex items-center justify-center">
                    
                    <!-- Animated Crimson Gradient Border Wrapper with Manas's Real Photo -->
                    <div class="animated-border-container hero-profile-ring w-72 h-72 sm:w-[26rem] sm:h-[26rem] lg:w-[29rem] lg:h-[29rem] shadow-neon-crimson">
                        <div class="profile-img-inner w-full h-full flex items-center justify-center">
                            <img src="data:image/jpeg;base64,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" 
                              alt="Manas Balkrishna Ippar" 
                              class="w-full h-full object-cover filter contrast-105 brightness-95">
                        </div>
                    </div>

                    <!-- Floating Glass Card 1 -->
                    <div class="absolute -top-4 -left-6 glass-card px-4 py-2.5 rounded-xl shadow-lg flex items-center gap-2 animate-bounce duration-1000">
                        <div class="w-8 h-8 rounded-lg bg-red-500/20 text-red-500 flex items-center justify-center text-sm">
                            <i class="fa-brands fa-java"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">Core Tech</div>
                            <div class="text-sm font-bold text-white">Java</div>
                        </div>
                    </div>

                    <!-- Floating Glass Card 2 -->
                    <div class="absolute top-1/2 -right-8 glass-card px-4 py-2.5 rounded-xl shadow-lg flex items-center gap-2">
                        <div class="w-8 h-8 rounded-lg bg-rose-500/20 text-rose-400 flex items-center justify-center text-sm">
                            <i class="fa-brands fa-python"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">Analytics</div>
                            <div class="text-sm font-bold text-white">Python</div>
                        </div>
                    </div>

                    <!-- Floating Glass Card 3 -->
                    <div class="absolute -bottom-4 left-6 glass-card px-4 py-2.5 rounded-xl shadow-lg flex items-center gap-2">
                        <div class="w-8 h-8 rounded-lg bg-red-600/20 text-red-400 flex items-center justify-center text-sm">
                            <i class="fa-solid fa-code"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">Domain</div>
                            <div class="text-sm font-bold text-white">Web Dev</div>
                        </div>
                    </div>

                </div>
            </div>

        </div>

        <!-- Scroll indicator -->
        <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 hidden md:flex flex-col items-center gap-2 text-gray-400 text-xs tracking-widest font-mono">
            <span>Scroll to explore</span>
            <i class="fa-solid fa-arrow-down animate-bounce text-red-500"></i>
        </div>
    </section>

    <section id="about" class="py-28 sm:py-32 px-4 sm:px-6 lg:px-8 relative">
        <div class="max-w-7xl mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-mono uppercase tracking-widest text-red-500 mb-3">Background & Profile</h2>
                <h3 class="text-3xl sm:text-4xl font-bold text-white mb-4">About Me</h3>
                <p class="text-gray-400 text-lg">Turning curiosity into practical technology.</p>
            </div>

            <!-- Clean, full-width glassmorphism bio card layout (Terminal removed entirely) -->
            <div class="max-w-4xl mx-auto glass-card p-10 sm:p-14 rounded-3xl relative overflow-hidden shadow-2xl border border-white/10">
                <div class="absolute top-0 right-0 w-64 h-64 bg-red-600/5 rounded-bl-full pointer-events-none"></div>
                
                <div class="flex items-center gap-3 mb-6">
                    <div class="w-10 h-10 rounded-xl bg-red-500/10 text-red-500 flex items-center justify-center text-lg">
                        <i class="fa-solid fa-user-tie"></i>
                    </div>
                    <div>
                        <h4 class="text-xl font-bold text-white">Professional Summary</h4>
                        <p class="text-xs text-gray-400 font-mono">Manas Balkrishna Ippar</p>
                    </div>
                </div>

                <div class="space-y-6 text-gray-300 text-base sm:text-lg leading-relaxed">
                    <p>
                        I am a BCS graduate and current MCS (AI & Data Science) student based in Pune, with a strong interest in software development, web development, AI and Data Science. I enjoy exploring how technology can be used to solve practical problems and create useful digital experiences.
                    </p>
                    <p>
                        Throughout my academic journey, I have worked with programming, web technologies, databases and application development. I am continuously improving my technical skills and looking forward to building real-world solutions.
                    </p>
                </div>

                <div class="mt-8 pt-6 border-t border-white/10 flex flex-wrap gap-6 text-sm text-gray-400">
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-location-dot text-red-500"></i>
                        <span>Pune, Maharashtra, India</span>
                    </div>
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-graduation-cap text-rose-400"></i>
                        <span>Bachelor of Computer Science (BCS) • MCS (AI & Data Science)</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="py-28 sm:py-32 px-4 sm:px-6 lg:px-8 relative bg-charcoal/40">
        <div class="max-w-7xl mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-mono uppercase tracking-widest text-red-500 mb-3">Expertise & Stack</h2>
                <h3 class="text-3xl sm:text-4xl font-bold text-white mb-4">Technical Skills</h3>
                <p class="text-gray-400 text-lg">Technologies I work with and continue to explore.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-7">
                
                <!-- Category 1: Programming -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-red-500/10 text-red-500 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-code"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">PROGRAMMING</h4>
                            <p class="text-xs text-gray-400">Core languages</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-brands fa-java text-red-500"></i> Java
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-brands fa-python text-yellow-400"></i> Python
                        </span>
                    </div>
                </div>

                <!-- Category 2: Web -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-rose-500/10 text-rose-400 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-globe"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">WEB</h4>
                            <p class="text-xs text-gray-400">Frontend & interfaces</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-rose-500/50 transition-colors">
                            <i class="fa-brands fa-html5 text-orange-500"></i> HTML5
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-rose-500/50 transition-colors">
                            <i class="fa-brands fa-css3-alt text-blue-500"></i> CSS3
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-rose-500/50 transition-colors">
                            <i class="fa-brands fa-js text-yellow-400"></i> JavaScript
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-rose-500/50 transition-colors">
                            <i class="fa-solid fa-mobile-screen text-red-400"></i> Responsive Web Design
                        </span>
                    </div>
                </div>

                <!-- Category 3: Database -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-red-600/10 text-red-500 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-database"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">DATABASE</h4>
                            <p class="text-xs text-gray-400">Storage & management</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-solid fa-server text-red-400"></i> SQL
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-solid fa-database text-rose-400"></i> PostgreSQL
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-solid fa-table-cells text-red-500"></i> Database Management
                        </span>
                    </div>
                </div>

                <!-- Category 4: Development -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-amber-500/10 text-amber-500 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-laptop-code"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">DEVELOPMENT</h4>
                            <p class="text-xs text-gray-400">Frameworks & concepts</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-amber-500/50 transition-colors">
                            <i class="fa-solid fa-leaf text-green-500"></i> Spring Boot
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-amber-500/50 transition-colors">
                            <i class="fa-solid fa-plug text-red-400"></i> JDBC
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-amber-500/50 transition-colors">
                            <i class="fa-solid fa-cubes text-red-500"></i> Maven
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-amber-500/50 transition-colors">
                            <i class="fa-solid fa-project-diagram text-rose-400"></i> Object-Oriented Programming
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-amber-500/50 transition-colors">
                            <i class="fa-solid fa-sitemap text-yellow-400"></i> Data Structures & Algorithms
                        </span>
                    </div>
                </div>

                <!-- Category 5: Tools -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-orange-500/10 text-orange-500 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-toolbox"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">TOOLS</h4>
                            <p class="text-xs text-gray-400">Version control & workflow</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-orange-500/50 transition-colors">
                            <i class="fa-brands fa-git-alt text-orange-500"></i> Git
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-orange-500/50 transition-colors">
                            <i class="fa-brands fa-github text-white"></i> GitHub
                        </span>
                    </div>
                </div>

                <!-- Category 6: AI / Data -->
                <div class="glass-card premium-card reveal p-7 rounded-2xl transition-all duration-300 hover:-translate-y-1">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="w-12 h-12 rounded-xl bg-red-500/10 text-red-500 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-brain"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-white">AI / DATA</h4>
                            <p class="text-xs text-gray-400">Data science basics</p>
                        </div>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-solid fa-chart-line text-red-400"></i> Basic Data Analysis
                        </span>
                        <span class="skill-chip px-3 py-1.5 rounded-lg bg-white/5 border border-white/10 text-gray-200 text-sm font-medium flex items-center gap-2 hover:border-red-500/50 transition-colors">
                            <i class="fa-solid fa-microchip text-rose-400"></i> AI & Data Science Fundamentals
                        </span>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <section id="project" class="py-28 sm:py-32 px-4 sm:px-6 lg:px-8 relative">
        <div class="max-w-7xl mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-mono uppercase tracking-widest text-red-500 mb-3">Portfolio Highlight</h2>
                <h3 class="text-3xl sm:text-4xl font-bold text-white mb-4">Featured Project</h3>
                <p class="text-gray-400 text-lg">Practical solutions designed and built with precision.</p>
            </div>

            <!-- Large Premium Project Card -->
            <div class="glass-card rounded-3xl p-8 sm:p-12 border border-white/10 shadow-2xl relative overflow-hidden">
                <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-red-600/10 rounded-full blur-3xl pointer-events-none"></div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 items-center">
                    
                    <!-- Project Details -->
                    <div class="lg:col-span-7 space-y-6">
                        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-red-500/10 text-red-400 text-xs font-mono">
                            <i class="fa-solid fa-square-parking"></i>
                            <span>Web Application</span>
                        </div>

                        <h4 class="text-3xl sm:text-4xl font-bold text-white tracking-tight">Smart Parking System</h4>

                        <p class="text-gray-300 text-base sm:text-lg leading-relaxed">
                            A smart web-based parking management system designed to make parking easier and more efficient. The system allows users to view available parking slots, select a suitable slot and use a payment option for parking.
                        </p>

                        <!-- Key Features bullet list -->
                        <div class="space-y-2 pt-2">
                            <div class="flex items-center gap-3 text-gray-300 text-sm">
                                <i class="fa-solid fa-check text-red-500"></i>
                                <span>Real-time parking slot availability checking</span>
                            </div>
                            <div class="flex items-center gap-3 text-gray-300 text-sm">
                                <i class="fa-solid fa-check text-red-500"></i>
                                <span>Interactive slot selection interface</span>
                            </div>
                            <div class="flex items-center gap-3 text-gray-300 text-sm">
                                <i class="fa-solid fa-check text-red-500"></i>
                                <span>Integrated digital payment option for reservations</span>
                            </div>
                        </div>

                        <div class="flex flex-wrap gap-2 pt-2">
                            <span class="px-3 py-1 rounded-md bg-white/5 text-xs text-gray-300 font-mono border border-white/10">HTML5 / CSS3</span>
                            <span class="px-3 py-1 rounded-md bg-white/5 text-xs text-gray-300 font-mono border border-white/10">JavaScript</span>
                            <span class="px-3 py-1 rounded-md bg-white/5 text-xs text-gray-300 font-mono border border-white/10">Database Management</span>
                            <span class="px-3 py-1 rounded-md bg-white/5 text-xs text-gray-300 font-mono border border-white/10">Web App</span>
                        </div>
                    </div>

                    <!-- Project Visual Mockup / Interactive Slot Simulator Preview -->
                    <div class="lg:col-span-5 bg-charcoal/90 rounded-2xl p-6 border border-white/10 relative">
                        <div class="flex items-center justify-between mb-4 pb-3 border-b border-white/10">
                            <div class="flex items-center gap-2 text-xs font-mono text-gray-400">
                                <span class="w-2.5 h-2.5 rounded-full bg-emerald-400"></span>
                                <span>Parking Matrix Preview</span>
                            </div>
                            <span class="text-xs text-red-500 font-mono">Live Simulator</span>
                        </div>

                        <!-- Mini Interactive Parking Slot Demo -->
                        <div class="grid grid-cols-3 gap-3 mb-6">
                            <button type="button" onclick="toggleSlot(this)" data-slot="A1" class="parking-slot w-full p-3 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-center cursor-pointer hover:bg-emerald-500/20 hover:-translate-y-0.5 transition-all focus:outline-none focus:ring-2 focus:ring-red-500/70">
                                <div class="text-xs text-emerald-400 font-mono">Slot A1</div>
                                <div class="text-xs text-gray-300 mt-1">Available</div>
                            </button>
                            <div class="p-3 rounded-xl bg-red-500/10 border border-red-500/30 text-center opacity-75 cursor-not-allowed">
                                <div class="text-xs text-red-400 font-mono">Slot A2</div>
                                <div class="text-xs text-gray-400 mt-1">Occupied</div>
                            </div>
                            <button type="button" onclick="toggleSlot(this)" data-slot="A3" class="parking-slot w-full p-3 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-center cursor-pointer hover:bg-emerald-500/20 hover:-translate-y-0.5 transition-all focus:outline-none focus:ring-2 focus:ring-red-500/70">
                                <div class="text-xs text-emerald-400 font-mono">Slot A3</div>
                                <div class="text-xs text-gray-300 mt-1">Available</div>
                            </button>
                        </div>

                        <div class="bg-red-500/10 border border-red-500/20 rounded-xl p-3.5 text-xs text-red-300 space-y-3">
                            <div class="flex items-center justify-between gap-3">
                                <span id="slot-status-text">Choose an available slot to preview a booking.</span>
                                <span id="slot-count" class="shrink-0 text-gray-400">2 available</span>
                            </div>
                            <div class="flex gap-2">
                                <button type="button" onclick="simulatePayment()" class="flex-1 px-3 py-2 bg-red-600 hover:bg-red-500 text-white rounded-lg font-medium transition-all hover:shadow-neon-crimson">
                                    Reserve Slot
                                </button>
                                <button type="button" onclick="resetParkingDemo()" class="px-3 py-2 bg-white/5 hover:bg-white/10 border border-white/10 text-gray-300 rounded-lg transition-colors" aria-label="Reset parking demo">
                                    Reset
                                </button>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="py-28 sm:py-32 px-4 sm:px-6 lg:px-8 relative bg-charcoal/40">
        <div class="max-w-7xl mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-mono uppercase tracking-widest text-red-500 mb-3">Get in Touch</h2>
                <h3 class="text-3xl sm:text-4xl font-bold text-white mb-4">Let's Connect</h3>
                <p class="text-gray-400 text-lg">Have an opportunity or project in mind? Reach out and let's talk.</p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-10">
                
                <!-- Contact info cards -->
                <div class="lg:col-span-5 space-y-6">
                    <div class="glass-card p-7 rounded-2xl flex items-center gap-4">
                        <div class="w-12 h-12 rounded-xl bg-red-500/10 text-red-500 flex items-center justify-center text-lg">
                            <i class="fa-solid fa-envelope"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">Email Me</div>
                            <div class="flex items-center gap-3"><a href="mailto:manasippar4@gmail.com" class="text-white font-medium hover:text-red-500 transition-colors">manasippar4@gmail.com</a><button type="button" class="copy-btn text-xs text-gray-400 hover:text-red-400" data-copy="manasippar4@gmail.com" aria-label="Copy email"><i class="fa-regular fa-copy"></i></button></div>
                        </div>
                    </div>

                    <div class="glass-card p-7 rounded-2xl flex items-center gap-4">
                        <div class="w-12 h-12 rounded-xl bg-rose-500/10 text-rose-400 flex items-center justify-center text-lg">
                            <i class="fa-solid fa-location-dot"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">Location</div>
                            <div class="text-white font-medium">Pune, Maharashtra, India</div>
                        </div>
                    </div>

                    <div class="glass-card p-7 rounded-2xl flex items-center gap-4">
                        <div class="w-12 h-12 rounded-xl bg-red-600/10 text-red-500 flex items-center justify-center text-lg">
                            <i class="fa-brands fa-linkedin-in"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">LinkedIn Profile</div>
                            <a href="https://www.linkedin.com/in/manas-ippar-07b004329" target="_blank" rel="noopener noreferrer" class="text-white font-medium hover:text-red-500 transition-colors">View Profile &rarr;</a>
                        </div>
                    </div>

                    <div class="glass-card p-7 rounded-2xl flex items-center gap-4">
                        <div class="w-12 h-12 rounded-xl bg-gray-500/10 text-gray-300 flex items-center justify-center text-lg">
                            <i class="fa-brands fa-github"></i>
                        </div>
                        <div>
                            <div class="text-xs text-gray-400 font-mono">GitHub Repository</div>
                            <a href="https://share.google/0Renry8I3rSxdHjFz" target="_blank" rel="noopener noreferrer" class="text-white font-medium hover:text-red-500 transition-colors">View Repositories &rarr;</a>
                        </div>
                    </div>
                </div>

                <!-- Contact Form -->
                <div class="lg:col-span-7 glass-card p-8 sm:p-10 rounded-3xl border border-white/10">
                    <form id="contact-form" onsubmit="handleFormSubmit(event)" class="space-y-6">
                        <div>
                            <label class="block text-xs font-mono text-gray-400 uppercase tracking-wider mb-2" for="name">Your Name</label>
                            <input type="text" id="name" required placeholder="Enter your name" 
                                class="w-full px-4 py-3 rounded-xl bg-darkBg/90 border border-white/10 text-white placeholder-gray-500 focus:outline-none focus:border-red-500 transition-colors">
                        </div>

                        <div>
                            <label class="block text-xs font-mono text-gray-400 uppercase tracking-wider mb-2" for="email">Your Email</label>
                            <input type="email" id="email" required placeholder="Enter your email address" 
                                class="w-full px-4 py-3 rounded-xl bg-darkBg/90 border border-white/10 text-white placeholder-gray-500 focus:outline-none focus:border-red-500 transition-colors">
                        </div>

                        <div>
                            <label class="block text-xs font-mono text-gray-400 uppercase tracking-wider mb-2" for="message">Message</label>
                            <textarea id="message" rows="5" required placeholder="Write your message here..." 
                                class="w-full px-4 py-3 rounded-xl bg-darkBg/90 border border-white/10 text-white placeholder-gray-500 focus:outline-none focus:border-red-500 transition-colors"></textarea>
                        </div>

                        <button type="submit" class="w-full py-4 rounded-xl bg-red-600 hover:bg-red-500 text-white font-medium transition-all shadow-neon-crimson flex items-center justify-center gap-2">
                            <span>Send Message</span>
                            <i class="fa-regular fa-paper-plane text-sm"></i>
                        </button>

                        <div id="form-success-msg" class="hidden p-4 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-emerald-300 text-sm text-center">
                            Thank you! Your message has been prepared. You can also reach Manas directly at <span class="font-semibold underline">manasippar4@gmail.com</span>.
                        </div>
                    </form>
                </div>

            </div>
        </div>
    </section>

    <button id="back-to-top" type="button" aria-label="Back to top" title="Back to top" class="fixed bottom-6 right-6 z-40 w-12 h-12 rounded-full glass-card text-gray-300 hover:text-white hover:border-red-500/60 opacity-0 translate-y-4 pointer-events-none transition-all duration-300 shadow-lg">
        <i class="fa-solid fa-arrow-up"></i>
    </button>


    <button id="back-top" class="back-top" type="button" aria-label="Back to top" title="Back to top">
        <i class="fa-solid fa-arrow-up"></i>
    </button>

    <footer class="py-12 border-t border-white/10 text-center text-sm text-gray-400">
        <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
            <div class="font-mono text-white font-bold">
                MANAS BALKRISHNA IPPAR
            </div>
            <div>
                &copy; 2026 • BCS Graduate • MCS (AI & Data Science) Student • Software Developer. All rights reserved.
            </div>
            <div class="flex items-center gap-4 text-lg">
                <a href="https://www.linkedin.com/in/manas-ippar-07b004329" target="_blank" rel="noopener noreferrer" class="hover:text-red-500 transition-colors" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="https://share.google/0Renry8I3rSxdHjFz" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors" aria-label="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="mailto:manasippar4@gmail.com" class="hover:text-red-400 transition-colors" aria-label="Email"><i class="fa-solid fa-envelope"></i></a>
            </div>
        </div>
    </footer>


    <script>
        const $ = (selector, root = document) => root.querySelector(selector);
        const $$ = (selector, root = document) => [...root.querySelectorAll(selector)];

        const mobileMenuBtn = $('#mobile-menu-btn');
        const mobileMenu = $('#mobile-menu');
        const mobileLinks = $$('.mobile-link');

        function closeMobileMenu() {
            if (!mobileMenu) return;
            mobileMenu.classList.add('hidden');
            if (mobileMenuBtn) mobileMenuBtn.innerHTML = '<i class="fa-solid fa-bars text-xl"></i>';
        }
        mobileMenuBtn?.addEventListener('click', () => {
            const open = !mobileMenu.classList.contains('hidden');
            mobileMenu.classList.toggle('hidden');
            mobileMenuBtn.innerHTML = open ? '<i class="fa-solid fa-bars text-xl"></i>' : '<i class="fa-solid fa-xmark text-xl"></i>';
        });
        mobileLinks.forEach(link => link.addEventListener('click', closeMobileMenu));
        document.addEventListener('keydown', e => { if (e.key === 'Escape') closeMobileMenu(); });

        let toastTimer;
        function showToast(message) {
            const toast = $('#toast');
            if (!toast) return;
            toast.textContent = message;
            toast.classList.add('show');
            clearTimeout(toastTimer);
            toastTimer = setTimeout(() => toast.classList.remove('show'), 2800);
        }

        const progress = $('#scroll-progress');
        const backTop = $('#back-top');
        const navLinks = $$('header nav a');
        function updateScrollUI() {
            const max = document.documentElement.scrollHeight - window.innerHeight;
            if (progress) progress.style.width = `${max > 0 ? (window.scrollY / max) * 100 : 0}%`;
            backTop?.classList.toggle('show', window.scrollY > 650);
            let current = '';
            $$('section[id]').forEach(section => {
                if (window.scrollY >= section.offsetTop - 150) current = section.id;
            });
            navLinks.forEach(link => {
                const active = link.getAttribute('href') === `#${current}`;
                link.classList.toggle('text-red-500', active);
                if (active) link.setAttribute('aria-current', 'page');
                else link.removeAttribute('aria-current');
            });
        }
        window.addEventListener('scroll', updateScrollUI, { passive: true });
        updateScrollUI();
        backTop?.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

        const revealItems = $$('.reveal');
        if ('IntersectionObserver' in window) {
            const observer = new IntersectionObserver((entries, obs) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                        obs.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.12 });
            revealItems.forEach(item => observer.observe(item));
        } else revealItems.forEach(item => item.classList.add('is-visible'));

        const typingText = $('#typing-text');
        const phrases = ['digital experiences.', 'smart web applications.', 'practical solutions.', 'clean user interfaces.'];
        let phraseIndex = 0, charIndex = 0, deleting = false;
        function typeLoop() {
            if (!typingText) return;
            const phrase = phrases[phraseIndex];
            typingText.textContent = deleting ? phrase.slice(0, charIndex--) : phrase.slice(0, charIndex++);
            let delay = deleting ? 45 : 75;
            if (!deleting && charIndex > phrase.length) { deleting = true; delay = 1500; }
            else if (deleting && charIndex < 0) { deleting = false; phraseIndex = (phraseIndex + 1) % phrases.length; charIndex = 0; delay = 350; }
            setTimeout(typeLoop, delay);
        }
        typeLoop();

        const cursorGlow = $('#cursor-glow');
        window.addEventListener('pointermove', e => {
            if (cursorGlow && window.innerWidth > 640) {
                cursorGlow.style.left = `${e.clientX}px`;
                cursorGlow.style.top = `${e.clientY}px`;
            }
        }, { passive: true });

        $$('.copy-btn').forEach(button => button.addEventListener('click', async () => {
            try {
                await navigator.clipboard.writeText(button.dataset.copy);
                showToast('Copied to clipboard.');
            } catch { showToast(button.dataset.copy); }
        }));

        const profileImg = $('.profile-img-inner img');
        profileImg?.addEventListener('error', () => {
            profileImg.removeAttribute('src');
            profileImg.alt = 'Professional profile photo';
            profileImg.style.background = 'linear-gradient(135deg,#18181b,#450a0a)';
        });

        let selectedSlot = null;
        const slotCards = $$('#project .grid-cols-3 > div');
        const slotStatus = $('#slot-status-text');
        function updateParkingStatus(message) { if (slotStatus) slotStatus.textContent = message; }

        window.toggleSlot = function(el) {
            if (el.classList.contains('bg-red-500/10')) return;
            slotCards.forEach(card => card.classList.remove('ring-2', 'ring-red-500', 'scale-[1.03]'));
            el.classList.add('ring-2', 'ring-red-500', 'scale-[1.03]');
            selectedSlot = el.querySelector('.font-mono')?.innerText || null;
            updateParkingStatus(selectedSlot ? `${selectedSlot} selected for booking` : 'Select a slot');
        };

        window.simulatePayment = function() {
            if (!selectedSlot) {
                updateParkingStatus('Please select an available slot first.');
                showToast('Choose an available parking slot.');
                return;
            }
            const booked = selectedSlot;
            updateParkingStatus(`Demo booking confirmed for ${booked}.`);
            showToast(`${booked} reserved in demo mode.`);
            setTimeout(() => {
                slotCards.forEach(card => card.classList.remove('ring-2', 'ring-red-500', 'scale-[1.03]'));
                selectedSlot = null;
                updateParkingStatus('Click an available slot to simulate selection');
            }, 3500);
        };

        window.handleFormSubmit = function(e) {
            e.preventDefault();
            const name = $('#name')?.value.trim();
            const email = $('#email')?.value.trim();
            const message = $('#message')?.value.trim();
            if (!name || !email || !message) {
                showToast('Please complete all fields.');
                return;
            }
            const subject = encodeURIComponent(`Portfolio enquiry from ${name}`);
            const body = encodeURIComponent(`Name: ${name}\nEmail: ${email}\n\nMessage:\n${message}`);
            window.location.href = `mailto:manasippar4@gmail.com?subject=${subject}&body=${body}`;
            const successMsg = $('#form-success-msg');
            if (successMsg) {
                successMsg.classList.remove('hidden');
                successMsg.innerHTML = 'Your email draft is ready. Please send it from your email app.';
            }
            $('#contact-form')?.reset();
            showToast('Email draft prepared.');
        };

        document.addEventListener('click', e => {
            const button = e.target.closest('button, a');
            if (!button || button.classList.contains('back-top')) return;
            button.animate([{ transform: 'scale(.98)' }, { transform: 'scale(1)' }], { duration: 120, easing: 'ease-out' });
        });
    </script>

</body>
</html>
