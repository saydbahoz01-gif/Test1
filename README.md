
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Calista Bakery</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        :root {
            --bg:#FDF6EE;--bg2:#F5EDE3;--fg:#2D1810;--fg2:#5A3D2E;
            --muted:#9B8578;--accent:#C87D3A;--accent2:#A65E20;
            --card:rgba(255,255,255,0.35);--card-border:rgba(255,255,255,0.5);
            --glass:rgba(255,255,255,0.18);--glass-border:rgba(255,255,255,0.35);
            --glass-strong:rgba(255,255,255,0.55);
            --shadow:rgba(45,24,16,0.08);--shadow2:rgba(45,24,16,0.15);
            --nav-bg:rgba(255,255,255,0.6);--nav-border:rgba(255,255,255,0.4);
            --overlay:rgba(45,24,16,0.4);--danger:#C62828;
            --blob1:rgba(200,125,58,0.15);--blob2:rgba(166,94,32,0.1);--blob3:rgba(233,196,106,0.12);
        }
        .dark {
            --bg:#1A1210;--bg2:#231A16;--fg:#F5EDE3;--fg2:#D4C4B0;
            --muted:#8B7B6B;--accent:#E8A84C;--accent2:#C87D3A;
            --card:rgba(255,255,255,0.06);--card-border:rgba(255,255,255,0.1);
            --glass:rgba(255,255,255,0.06);--glass-border:rgba(255,255,255,0.12);
            --glass-strong:rgba(255,255,255,0.1);
            --shadow:rgba(0,0,0,0.2);--shadow2:rgba(0,0,0,0.35);
            --nav-bg:rgba(26,18,16,0.75);--nav-border:rgba(255,255,255,0.08);
            --overlay:rgba(0,0,0,0.6);
            --blob1:rgba(232,168,76,0.08);--blob2:rgba(200,125,58,0.06);--blob3:rgba(233,196,106,0.05);
        }
        *{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
        html,body{width:100%;height:100%;overflow:hidden;font-family:'Noto Sans Arabic',sans-serif;background:var(--bg);color:var(--fg);transition:background .6s,color .4s;}

        .blob{position:fixed;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0;will-change:transform;}
        .blob-1{width:400px;height:400px;background:var(--blob1);top:-100px;right:-80px;animation:bf1 18s ease-in-out infinite;}
        .blob-2{width:350px;height:350px;background:var(--blob2);bottom:-50px;left:-100px;animation:bf2 22s ease-in-out infinite;}
        .blob-3{width:300px;height:300px;background:var(--blob3);top:40%;left:50%;transform:translateX(-50%);animation:bf3 15s ease-in-out infinite;}
        @keyframes bf1{0%,100%{transform:translate(0,0) scale(1);}25%{transform:translate(-60px,40px) scale(1.1);}50%{transform:translate(-30px,80px) scale(.95);}75%{transform:translate(40px,30px) scale(1.05);}}
        @keyframes bf2{0%,100%{transform:translate(0,0) scale(1);}33%{transform:translate(50px,-40px) scale(1.08);}66%{transform:translate(80px,20px) scale(.92);}}
        @keyframes bf3{0%,100%{transform:translateX(-50%) translate(0,0) scale(1);}50%{transform:translateX(-50%) translate(30px,-50px) scale(1.15);}}

        .liquid-glass{background:var(--glass);backdrop-filter:blur(24px) saturate(1.4);-webkit-backdrop-filter:blur(24px) saturate(1.4);border:1px solid var(--glass-border);border-radius:24px;box-shadow:0 8px 32px var(--shadow),inset 0 1px 0 rgba(255,255,255,.15);transition:all .4s cubic-bezier(.34,1.56,.64,1);}
        .liquid-glass:hover{box-shadow:0 12px 40px var(--shadow2),inset 0 1px 0 rgba(255,255,255,.2);transform:translateY(-2px);}

        .app-header{position:fixed;top:0;left:0;right:0;z-index:100;padding:12px 20px;background:var(--nav-bg);backdrop-filter:blur(30px) saturate(1.5);-webkit-backdrop-filter:blur(30px) saturate(1.5);border-bottom:1px solid var(--nav-border);display:flex;align-items:center;justify-content:space-between;transition:background .4s,border-color .4s;}
        .logo-text{font-size:1.25rem;font-weight:800;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
        .header-btn{width:38px;height:38px;border-radius:12px;background:var(--glass);border:1px solid var(--glass-border);display:flex;align-items:center;justify-content:center;color:var(--fg);cursor:pointer;transition:all .3s;font-size:.95rem;}
        .header-btn:hover{background:var(--glass-strong);transform:scale(1.08);}
        .header-btn:active{transform:scale(.95);}

        .app-nav{position:fixed;bottom:0;left:0;right:0;z-index:100;padding:6px 16px 12px;background:var(--nav-bg);backdrop-filter:blur(30px) saturate(1.6);-webkit-backdrop-filter:blur(30px) saturate(1.6);border-top:1px solid var(--nav-border);transition:background .4s,border-color .4s;}
        .nav-inner{display:flex;align-items:center;justify-content:space-around;max-width:400px;margin:0 auto;}
        .nav-item{display:flex;flex-direction:column;align-items:center;gap:3px;padding:8px 16px;border-radius:16px;cursor:pointer;position:relative;transition:all .4s cubic-bezier(.34,1.56,.64,1);color:var(--muted);font-size:.7rem;font-weight:500;background:transparent;border:none;min-width:72px;font-family:inherit;}
        .nav-item i{font-size:1.2rem;transition:all .4s cubic-bezier(.34,1.56,.64,1);}
        .nav-item.active{color:var(--accent);background:var(--glass-strong);box-shadow:0 4px 16px var(--shadow);}
        .nav-item.active i{transform:scale(1.15) translateY(-2px);}
        .nav-item:not(.active):hover{color:var(--fg2);}

        .pages-container{position:fixed;top:0;left:0;right:0;bottom:0;z-index:1;overflow:hidden;}
        .page{position:absolute;inset:0;padding:72px 16px 90px;overflow-y:auto;overflow-x:hidden;opacity:0;transform:translateY(30px) scale(.97);pointer-events:none;transition:opacity .5s,transform .5s cubic-bezier(.34,1.56,.64,1);-webkit-overflow-scrolling:touch;}
        .page.active{opacity:1;transform:translateY(0) scale(1);pointer-events:auto;}
        .page::-webkit-scrollbar{width:0;}

        .menu-tabs{display:flex;gap:8px;padding:8px 0 16px;overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;}
        .menu-tabs::-webkit-scrollbar{display:none;}
        .menu-tab{flex-shrink:0;padding:10px 20px;border-radius:14px;border:1px solid var(--glass-border);background:var(--glass);color:var(--muted);font-family:inherit;font-size:.85rem;font-weight:600;cursor:pointer;transition:all .35s cubic-bezier(.34,1.56,.64,1);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);}
        .menu-tab.active{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;border-color:transparent;box-shadow:0 4px 20px rgba(200,125,58,.35);transform:scale(1.03);}
        .menu-tab:not(.active):hover{background:var(--glass-strong);color:var(--fg);}

        .menu-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;padding-bottom:20px;}
        .menu-card{border-radius:20px;overflow:hidden;background:var(--card);border:1px solid var(--card-border);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);box-shadow:0 4px 20px var(--shadow);cursor:pointer;transition:all .4s cubic-bezier(.34,1.56,.64,1);animation:cardIn .5s ease both;}
        .menu-card:hover{transform:translateY(-4px) scale(1.02);box-shadow:0 8px 30px var(--shadow2);}
        .menu-card:active{transform:scale(.97);}
        .menu-card-img{width:100%;height:120px;object-fit:cover;transition:transform .5s;}
        .menu-card:hover .menu-card-img{transform:scale(1.08);}
        .menu-card-img-wrap{overflow:hidden;}
        .menu-card-body{padding:10px 12px 14px;}
        .menu-card-name{font-size:.85rem;font-weight:700;margin-bottom:4px;color:var(--fg);line-height:1.4;}
        .menu-card-price{font-size:.95rem;font-weight:800;color:var(--accent);}
        @keyframes cardIn{from{opacity:0;transform:translateY(20px) scale(.95);}to{opacity:1;transform:translateY(0) scale(1);}}

        .tables-title{font-size:1.5rem;font-weight:800;text-align:center;padding:20px 0 4px;}
        .tables-sub{text-align:center;color:var(--muted);font-size:.85rem;margin-bottom:20px;}
        .tables-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;padding-bottom:20px;}
        .table-card{aspect-ratio:1;border-radius:24px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;cursor:pointer;font-family:inherit;border:2px solid var(--glass-border);background:var(--glass);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);transition:all .4s cubic-bezier(.34,1.56,.64,1);animation:cardIn .5s ease both;}
        .table-card i{font-size:2rem;color:var(--muted);transition:all .4s;}
        .table-card span{font-size:.9rem;font-weight:700;color:var(--fg);}
        .table-card.selected{border-color:var(--accent);background:linear-gradient(135deg,rgba(200,125,58,.15),rgba(200,125,58,.05));box-shadow:0 0 30px rgba(200,125,58,.2);}
        .table-card.selected i{color:var(--accent);transform:scale(1.15);}
        .table-card:not(.selected):hover{border-color:var(--accent);transform:scale(1.04);}
        .table-card:active{transform:scale(.95);}

        .order-title{font-size:1.5rem;font-weight:800;text-align:center;padding:20px 0 4px;}
        .order-empty{text-align:center;padding:60px 20px;color:var(--muted);}
        .order-empty i{font-size:3rem;margin-bottom:12px;display:block;opacity:.4;}
        .order-table-badge{display:inline-flex;align-items:center;gap:8px;padding:8px 20px;border-radius:14px;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;font-weight:700;font-size:.9rem;margin:0 auto 16px;}
        .order-item{display:flex;align-items:center;gap:12px;padding:12px 14px;border-radius:16px;background:var(--card);border:1px solid var(--card-border);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);margin-bottom:8px;animation:slideIn .4s ease both;transition:all .3s;}
        @keyframes slideIn{from{opacity:0;transform:translateX(20px);}to{opacity:1;transform:translateX(0);}}
        .order-item-img{width:50px;height:50px;border-radius:12px;object-fit:cover;flex-shrink:0;}
        .order-item-info{flex:1;min-width:0;}
        .order-item-name{font-size:.82rem;font-weight:700;color:var(--fg);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
        .order-item-price{font-size:.78rem;color:var(--accent);font-weight:700;}
        .order-item-controls{display:flex;align-items:center;gap:6px;}
        .qty-btn{width:30px;height:30px;border-radius:10px;border:1px solid var(--glass-border);background:var(--glass);color:var(--fg);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.85rem;font-weight:700;transition:all .3s;font-family:inherit;}
        .qty-btn:hover{background:var(--glass-strong);transform:scale(1.1);}
        .qty-btn:active{transform:scale(.9);}
        .qty-btn.remove{color:var(--danger);}
        .qty-num{font-size:.9rem;font-weight:800;min-width:20px;text-align:center;color:var(--fg);}

        .order-total{display:flex;justify-content:space-between;align-items:center;padding:16px 18px;border-radius:18px;background:var(--glass-strong);border:1px solid var(--glass-border);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);margin:16px 0;}
        .order-total-label{font-weight:700;font-size:.95rem;color:var(--fg);}
        .order-total-value{font-weight:900;font-size:1.2rem;color:var(--accent);}

        .send-btn{width:100%;padding:16px;border-radius:18px;border:none;font-family:inherit;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;font-size:1.05rem;font-weight:800;cursor:pointer;box-shadow:0 6px 24px rgba(200,125,58,.35);transition:all .4s cubic-bezier(.34,1.56,.64,1);}
        .send-btn:hover{transform:translateY(-2px) scale(1.01);box-shadow:0 10px 30px rgba(200,125,58,.45);}
        .send-btn:active{transform:scale(.97);}
        .send-btn:disabled{opacity:.4;cursor:not-allowed;transform:none;box-shadow:none;}

        .gallery-title{font-size:1.5rem;font-weight:800;text-align:center;padding:20px 0 16px;}
        .gallery-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;padding-bottom:20px;}
        .gallery-item{aspect-ratio:1;border-radius:20px;overflow:hidden;cursor:pointer;position:relative;animation:cardIn .5s ease both;transition:all .4s cubic-bezier(.34,1.56,.64,1);}
        .gallery-item.span-2{grid-column:span 2;aspect-ratio:2/1;}
        .gallery-item img{width:100%;height:100%;object-fit:cover;transition:transform .5s;}
        .gallery-item:hover{transform:scale(1.02);}
        .gallery-item:hover img{transform:scale(1.1);}
        .gallery-item::after{content:'';position:absolute;inset:0;background:linear-gradient(to top,rgba(0,0,0,.35) 0%,transparent 50%);opacity:0;transition:opacity .3s;pointer-events:none;}
        .gallery-item:hover::after{opacity:1;}

        .gallery-dl-btn{position:absolute;bottom:10px;left:50%;transform:translateX(-50%) translateY(10px);padding:8px 16px;border-radius:12px;background:rgba(255,255,255,.85);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);border:1px solid rgba(255,255,255,.5);color:#2D1810;font-size:.75rem;font-weight:700;font-family:inherit;cursor:pointer;display:flex;align-items:center;gap:6px;opacity:0;pointer-events:none;transition:all .35s cubic-bezier(.34,1.56,.64,1);z-index:5;box-shadow:0 4px 16px rgba(0,0,0,.15);}
        .dark .gallery-dl-btn{background:rgba(30,20,16,.85);color:#F5EDE3;border-color:rgba(255,255,255,.1);}
        .gallery-item:hover .gallery-dl-btn{opacity:1;pointer-events:auto;transform:translateX(-50%) translateY(0);}
        .gallery-dl-btn:hover{transform:translateX(-50%) scale(1.06)!important;}
        .gallery-dl-btn:active{transform:translateX(-50%) scale(.95)!important;}
        .gallery-dl-btn.downloading{pointer-events:none;background:rgba(46,125,50,.9)!important;color:#fff!important;}

        .modal-overlay{position:fixed;inset:0;z-index:200;background:var(--overlay);backdrop-filter:blur(8px);-webkit-backdrop-filter:blur(8px);display:flex;align-items:flex-end;justify-content:center;opacity:0;pointer-events:none;transition:opacity .35s;}
        .modal-overlay.open{opacity:1;pointer-events:auto;}
        .modal-sheet{width:100%;max-width:500px;max-height:85vh;background:var(--bg);border-radius:28px 28px 0 0;padding:0 20px 30px;transform:translateY(100%);transition:transform .45s cubic-bezier(.34,1.56,.64,1);overflow-y:auto;}
        .modal-overlay.open .modal-sheet{transform:translateY(0);}
        .modal-handle{width:40px;height:4px;border-radius:2px;background:var(--muted);opacity:.4;margin:12px auto 16px;}
        .modal-img{width:100%;height:200px;object-fit:cover;border-radius:20px;margin-bottom:16px;}
        .modal-name{font-size:1.3rem;font-weight:800;margin-bottom:4px;color:var(--fg);}
        .modal-price{font-size:1.2rem;font-weight:900;color:var(--accent);margin-bottom:16px;}
        .modal-add-btn{width:100%;padding:14px;border-radius:16px;border:none;font-family:inherit;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;font-size:1rem;font-weight:700;cursor:pointer;box-shadow:0 4px 20px rgba(200,125,58,.3);transition:all .3s;display:flex;align-items:center;justify-content:center;gap:8px;}
        .modal-add-btn:hover{transform:scale(1.02);}
        .modal-add-btn:active{transform:scale(.97);}

        .gallery-modal{position:fixed;inset:0;z-index:400;background:rgba(0,0,0,.92);display:flex;flex-direction:column;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity .35s;}
        .gallery-modal.open{opacity:1;pointer-events:auto;}
        .gallery-modal img{max-width:95%;max-height:70vh;border-radius:16px;object-fit:contain;}
        .gallery-modal.open img{animation:modalImgIn .4s cubic-bezier(.34,1.56,.64,1) both;}
        @keyframes modalImgIn{from{transform:scale(.85);opacity:0;}to{transform:scale(1);opacity:1;}}
        .gallery-modal-close{position:absolute;top:16px;right:16px;width:40px;height:40px;border-radius:50%;background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.2);color:#fff;font-size:1rem;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .3s;backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);}
        .gallery-modal-close:hover{background:rgba(255,255,255,.25);transform:scale(1.1);}
        .gallery-modal-dl{position:absolute;bottom:30px;padding:14px 32px;border-radius:16px;background:linear-gradient(135deg,var(--accent),var(--accent2));border:none;color:#fff;font-family:inherit;font-size:.95rem;font-weight:700;cursor:pointer;display:flex;align-items:center;gap:10px;box-shadow:0 6px 24px rgba(200,125,58,.4);transition:all .35s cubic-bezier(.34,1.56,.64,1);}
        .gallery-modal-dl:hover{transform:scale(1.05);}
        .gallery-modal-dl:active{transform:scale(.95);}
        .gallery-modal-dl.downloading{background:linear-gradient(135deg,#2E7D32,#1B5E20)!important;pointer-events:none;}

        .toast-container{position:fixed;top:70px;left:50%;transform:translateX(-50%);z-index:500;display:flex;flex-direction:column;gap:8px;align-items:center;pointer-events:none;}
        .toast{padding:12px 24px;border-radius:14px;background:var(--glass-strong);border:1px solid var(--glass-border);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);color:var(--fg);font-size:.85rem;font-weight:600;box-shadow:0 8px 30px var(--shadow2);animation:toastIn .4s ease both;white-space:nowrap;}
        .toast.out{animation:toastOut .35s ease both;}
        @keyframes toastIn{from{opacity:0;transform:translateY(-20px) scale(.9);}to{opacity:1;transform:translateY(0) scale(1);}}
        @keyframes toastOut{from{opacity:1;transform:translateY(0) scale(1);}to{opacity:0;transform:translateY(-20px) scale(.9);}}

        .dropdown{position:absolute;top:50px;right:0;min-width:140px;padding:6px;border-radius:16px;background:var(--bg);border:1px solid var(--glass-border);backdrop-filter:blur(24px);-webkit-backdrop-filter:blur(24px);box-shadow:0 12px 40px var(--shadow2);opacity:0;transform:translateY(-10px) scale(.95);pointer-events:none;transition:all .3s cubic-bezier(.34,1.56,.64,1);z-index:110;}
        .dropdown.open{opacity:1;transform:translateY(0) scale(1);pointer-events:auto;}
        .dropdown-item{display:flex;align-items:center;gap:10px;padding:10px 14px;border-radius:12px;cursor:pointer;font-size:.82rem;font-weight:600;color:var(--fg);transition:all .2s;border:none;background:none;width:100%;font-family:inherit;text-align:inherit;}
        .dropdown-item:hover{background:var(--glass);}
        .dropdown-item.active{color:var(--accent);}

        .splash-screen{position:fixed;inset:0;z-index:600;background:var(--bg);display:flex;flex-direction:column;align-items:center;justify-content:center;transition:opacity .6s,transform .6s;}
        .splash-screen.hide{opacity:0;transform:scale(1.1);pointer-events:none;}
        .splash-logo{font-size:2.2rem;font-weight:900;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;animation:sp 1.5s ease-in-out infinite;}
        .splash-sub{color:var(--muted);font-size:.85rem;margin-top:8px;}
        @keyframes sp{0%,100%{transform:scale(1);}50%{transform:scale(1.05);}}

        .content-center{max-width:500px;margin:0 auto;}
        .cart-badge{position:absolute;top:-4px;right:-4px;width:18px;height:18px;border-radius:50%;background:var(--danger);color:#fff;font-size:.6rem;font-weight:800;display:flex;align-items:center;justify-content:center;transform:scale(0);transition:transform .3s cubic-bezier(.34,1.56,.64,1);}
        .cart-badge.show{transform:scale(1);}

        @media(max-width:380px){.menu-grid{gap:8px;}.tables-grid{gap:8px;}.menu-card-img{height:100px;}.nav-item{padding:8px 10px;min-width:60px;}}
    </style>
</head>
<body>
    <div class="splash-screen" id="splash">
        <div class="splash-logo">Calista Bakery</div>
        <div class="splash-sub" data-i18n="welcome">بەخێربێیت</div>
    </div>

    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>
    <div class="toast-container" id="toastContainer"></div>

    <header class="app-header">
        <div class="logo-text">Calista Bakery</div>
        <div style="display:flex;gap:8px;align-items:center;">
            <div style="position:relative;">
                <button class="header-btn" onclick="toggleDropdown('langDropdown')" aria-label="زمان"><i class="fas fa-globe"></i></button>
                <div class="dropdown" id="langDropdown">
                    <button class="dropdown-item active" data-lang="ku" onclick="setLang('ku')"><span>کوردی</span></button>
                    <button class="dropdown-item" data-lang="ar" onclick="setLang('ar')"><span>العربية</span></button>
                    <button class="dropdown-item" data-lang="en" onclick="setLang('en')"><span>English</span></button>
                </div>
            </div>
            <button class="header-btn" onclick="toggleTheme()" aria-label="تاریک/ڕوناک"><i class="fas fa-moon" id="themeIcon"></i></button>
        </div>
    </header>

    <div class="pages-container">
        <div class="page active" id="pageTables">
            <div class="content-center">
                <div class="tables-title" data-i18n="tables">مێزەکان</div>
                <div class="tables-sub" data-i18n="selectTable">تکایە مێزێک هەڵبژێرە</div>
                <div class="tables-grid" id="tablesGrid"></div>
            </div>
        </div>
        <div class="page" id="pageOrder">
            <div class="content-center">
                <div class="order-title" data-i18n="order">ئۆردەر</div>
                <div style="text-align:center;margin-bottom:12px;">
                    <span class="order-table-badge" id="orderTableBadge" style="display:none;"><i class="fas fa-utensils"></i><span id="orderTableName"></span></span>
                </div>
                <div id="orderContent"></div>
            </div>
        </div>
        <div class="page" id="pageGallery">
            <div class="content-center">
                <div class="gallery-title" data-i18n="gallery">گەلەری</div>
                <div class="gallery-grid" id="galleryGrid"></div>
            </div>
        </div>
    </div>

    <div class="modal-overlay" id="itemModal" onclick="closeModal(event)">
        <div class="modal-sheet" onclick="event.stopPropagation()">
            <div class="modal-handle"></div>
            <img class="modal-img" id="modalImg" src="" alt="">
            <div class="modal-name" id="modalName"></div>
            <div class="modal-price" id="modalPrice"></div>
            <button class="modal-add-btn" onclick="addItemFromModal()">
                <i class="fas fa-plus"></i>
                <span data-i18n="addToOrder">زیادکردن بۆ ئۆردەر</span>
            </button>
        </div>
    </div>

    <div class="gallery-modal" id="galleryModal">
        <button class="gallery-modal-close" onclick="closeGalleryModal()"><i class="fas fa-times"></i></button>
        <img id="galleryModalImg" src="" alt="Calista Bakery">
        <button class="gallery-modal-dl" id="galleryModalDl" onclick="downloadGalleryImage()">
            <i class="fas fa-download"></i>
            <span data-i18n="downloadHQ">دانلۆد بە کوالێتی بەرز</span>
        </button>
    </div>

    <nav class="app-nav">
        <div class="nav-inner">
            <button class="nav-item active" data-page="pageTables" onclick="navigateTo('pageTables')">
                <i class="fas fa-chair"></i>
                <span data-i18n="tables">مێزەکان</span>
            </button>
            <button class="nav-item" data-page="pageOrder" onclick="navigateTo('pageOrder')" style="position:relative;">
                <i class="fas fa-receipt"></i>
                <span data-i18n="order">ئۆردەر</span>
                <span class="cart-badge" id="cartBadge">0</span>
            </button>
            <button class="nav-item" data-page="pageGallery" onclick="navigateTo('pageGallery')">
                <i class="fas fa-images"></i>
                <span data-i18n="gallery">گەلەری</span>
            </button>
        </div>
    </nav>

    <script>
    const i18n = {
        ku:{tables:"مێزەکان",order:"ئۆردەر",gallery:"گەلەری",selectTable:"تکایە مێزێک هەڵبژێرە",cake:"کێک",sweets:"شیرینی",coffee:"خواردنەوەی قاوە",cold:"خواردنەوەی سارد",addToOrder:"زیادکردن بۆ ئۆردەر",send:"ناردن بۆ وەتسئەپ",total:"کۆی گشتی",orderEmpty:"هیچ ئایتمێک نییە",orderEmptySub:"لە مێزەکان دەست پێ بکە و شتەکان زیاد بکە",tablePrefix:"مێزی",added:"زیادکرا",removed:"لابرا",orderSent:"ئۆردەرەکەت نێردرا!",selectTableFirst:"تکایە سەرەتا مێزێک هەڵبژێرە",orderMsg:"ئۆردەری نوێ:\n",items:"بڕ",dinar:"دینار",welcome:"بەخێربێیت",downloadHQ:"دانلۆد بە کوالێتی بەرز",downloading:"داگیرکار...",addMore:"زیادکردنی زیاتر"},
        ar:{tables:"الطاولات",order:"الطلب",gallery:"المعرض",selectTable:"يرجى اختيار طاولة",cake:"كيك",sweets:"حلويات",coffee:"قهوة",cold:"مشروبات باردة",addToOrder:"إضافة للطلب",send:"إرسال عبر واتساب",total:"المجموع الكلي",orderEmpty:"لا توجد عناصر",orderEmptySub:"ابدأ من الطاولات وأضف العناصر",tablePrefix:"طاولة",added:"تمت الإضافة",removed:"تمت الإزالة",orderSent:"تم إرسال طلبك!",selectTableFirst:"يرجى اختيار طاولة أولاً",orderMsg:"طلب جديد:\n",items:"كمية",dinar:"دينار",welcome:"مرحباً",downloadHQ:"تحميل بجودة عالية",downloading:"جاري التحميل...",addMore:"إضافة المزيد"},
        en:{tables:"Tables",order:"Order",gallery:"Gallery",selectTable:"Please select a table",cake:"Cake",sweets:"Sweets",coffee:"Coffee",cold:"Cold Drinks",addToOrder:"Add to Order",send:"Send via WhatsApp",total:"Total",orderEmpty:"No items yet",orderEmptySub:"Start from tables and add items",tablePrefix:"Table",added:"Added",removed:"Removed",orderSent:"Your order has been sent!",selectTableFirst:"Please select a table first",orderMsg:"New Order:\n",items:"Qty",dinar:"IQD",welcome:"Welcome",downloadHQ:"Download High Quality",downloading:"Downloading...",addMore:"Add More"}
    };

    const menuData = {
        cake:[
            {id:'c1',name:{ku:'کێکی شکلات',ar:'كيك شوكولاتة',en:'Chocolate Cake'},price:5000,img:'https://z-cdn-media.chatglm.cn/files/2488494f-9abf-477b-a56f-fe284296e6a0.png'},
            {id:'c2',name:{ku:'کێکی توت',ar:'كيك توت',en:'Berry Cake'},price:6000,img:'https://z-cdn-media.chatglm.cn/files/36a998d4-a5ce-4198-97f4-4e022528bd93.png'},
            {id:'c3',name:{ku:'کێکی ڤانێلا',ar:'كيك فانيلا',en:'Vanilla Cake'},price:4500,img:'https://z-cdn-media.chatglm.cn/files/0b6fe5c2-6c85-45da-8d91-77fb8ed63383.png'},
            {id:'c4',name:{ku:'کێکی مۆر',ar:'كيك جزر',en:'Carrot Cake'},price:5500,img:'https://z-cdn-media.chatglm.cn/files/df1b69f0-d65e-4ff2-913f-7d399ce3f59e.png'},
            {id:'c5',name:{ku:'کێکی رێدڤێڵڤێت',ar:'كيك ريد فيلفيت',en:'Red Velvet Cake'},price:7000,img:'https://z-cdn-media.chatglm.cn/files/dc9c313b-a23b-4d1a-8e92-0ccfe940e78f.png'},
            {id:'c6',name:{ku:'کێکی لەدایکبوون',ar:'كيك عيد ميلاد',en:'Birthday Cake'},price:8000,img:'https://z-cdn-media.chatglm.cn/files/acb7fe28-d5a4-472b-a88c-e31663fde6b2.png'}
        ],
        sweets:[
            {id:'s1',name:{ku:'کرواسان',ar:'كرواسان',en:'Croissant'},price:2500,img:'https://z-cdn-media.chatglm.cn/files/cba1e7e4-7ea2-4ef1-975c-d98c00feee6a.png'},
            {id:'s2',name:{ku:'باقلوا',ar:'باقلوا',en:'Baklava'},price:3000,img:'https://z-cdn-media.chatglm.cn/files/c36bde54-06b4-4dc5-9da6-c5b2aa451a3d.png'},
            {id:'s3',name:{ku:'کنافە',ar:'كنافة',en:'Kunafa'},price:4000,img:'https://z-cdn-media.chatglm.cn/files/8afb5b3f-e8c5-4b07-9adf-6f386a400da7.png'},
            {id:'s4',name:{ku:'ماکارۆن',ar:'ماكارون',en:'Macaron'},price:3500,img:'https://z-cdn-media.chatglm.cn/files/f4f7ef63-4857-4755-a0e1-2b25f56d7e06.png'},
            {id:'s5',name:{ku:'تیلادەنگ',ar:'حلوى دنج',en:'Halva'},price:2000,img:'https://z-cdn-media.chatglm.cn/files/f433b8ec-c7cd-448f-b608-7a8d31c0eeaf.png'},
            {id:'s6',name:{ku:'بۆنیتۆ',ar:'بونيتو',en:'Bonito'},price:2500,img:'https://z-cdn-media.chatglm.cn/files/ac24d75d-f4f7-4c86-b793-6c4b0abb2124.png'}
        ],
        coffee:[
            {id:'co1',name:{ku:'ئێسپرێسۆ',ar:'إسبريسو',en:'Espresso'},price:2000,img:'https://z-cdn-media.chatglm.cn/files/4edffd6d-13c1-40ad-acea-8b433a824453.png'},
            {id:'co2',name:{ku:'لاتێ',ar:'لاتيه',en:'Latte'},price:3000,img:'https://z-cdn-media.chatglm.cn/files/3bcb4dc9-82b6-4fb3-90b7-e6b10f2049c6.png'},
            {id:'co3',name:{ku:'کاپوچینۆ',ar:'كابتشينو',en:'Cappuccino'},price:3000,img:'https://z-cdn-media.chatglm.cn/files/e4914c5d-085c-4162-bce5-f7a1cb51b3dc.png'},
            {id:'co4',name:{ku:'مۆکا',ar:'موكا',en:'Mocha'},price:3500,img:'https://z-cdn-media.chatglm.cn/files/cbf84bf8-85a0-4529-84bd-690ae08b0168.png'},
            {id:'co5',name:{ku:'ئەمریکانۆ',ar:'أمريكانو',en:'Americano'},price:2500,img:'https://z-cdn-media.chatglm.cn/files/81b5a1e7-1538-4447-9726-422e5df8a439.png'},
            {id:'co6',name:{ku:'فراپێ',ar:'فرابيه',en:'Frappé'},price:3500,img:'https://z-cdn-media.chatglm.cn/files/02c725dc-42b4-43c9-bd2f-b7a5be724ef2.png'}
        ],
        cold:[
            {id:'d1',name:{ku:'لیمۆنادە',ar:'ليمونادة',en:'Lemonade'},price:2500,img:'https://z-cdn-media.chatglm.cn/files/5000c3fc-d78e-4d61-9a83-f6d84ed5104d.png'},
            {id:'d2',name:{ku:'موجیتۆ',ar:'موهيتو',en:'Mojito'},price:3000,img:'https://z-cdn-media.chatglm.cn/files/24541054-a820-4522-83eb-1e9c9f3b45c9.png'},
            {id:'d3',name:{ku:'شەربەتی توت',ar:'عصير توت',en:'Berry Juice'},price:2000,img:'https://z-cdn-media.chatglm.cn/files/2219536f-c341-41d5-89b3-5dd692518d2c.png'},
            {id:'d4',name:{ku:'آیس تی',ar:'شاي مثلج',en:'Iced Tea'},price:2000,img:'https://z-cdn-media.chatglm.cn/files/01dc8366-0f46-4029-846e-307639891c73.png'},
            {id:'d5',name:{ku:'سمووزی میوە',ar:'سموذي فواكه',en:'Fruit Smoothie'},price:3500,img:'https://z-cdn-media.chatglm.cn/files/2a8bc841-90d0-4ec8-b720-45646d354629.png'},
            {id:'d6',name:{ku:'شەربەتی پرتەقاڵ',ar:'عصير برتقال',en:'Orange Juice'},price:2500,img:'https://z-cdn-media.chatglm.cn/files/9aab41d7-577e-47f1-8171-aada3f6687d7.png'}
        ]
    };

    const galleryImages=[
        {img:'https://z-cdn-media.chatglm.cn/files/e06e1c5e-85ea-416b-be34-da09390c99e8.png', span:true},
        {img:'https://z-cdn-media.chatglm.cn/files/2db151d1-9291-4ab5-ae85-521ad4f91bbf.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/14af3512-0896-41ff-897c-521d04b9a818.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/9104fb65-d8c6-4670-b1b4-b437e0e36b78.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/959981b8-d2c0-42de-9107-7678aef5bd49.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/f6124b66-52c7-45c2-911c-96588a8833fc.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/3b08c0bc-3af7-4375-aa9c-a13f8b261d73.png', span:true},
        {img:'https://z-cdn-media.chatglm.cn/files/c9be1848-9d8c-4cbb-a22f-ca76ebdc0dcd.png', span:false},
        {img:'https://z-cdn-media.chatglm.cn/files/2a7610ac-1fec-464c-b50c-29131bcbec06.png', span:false}
    ];

    let state={currentPage:'pageTables',selectedTable:null,cart:[],lang:'ku',dark:false,openDropdown:null,modalItem:null,galleryModalSrc:null};
    let activeMenuCat='cake';

    setTimeout(()=>{document.getElementById('splash').classList.add('hide');},1200);

    function navigateTo(p){
        if(state.currentPage===p)return;
        state.currentPage=p;
        document.querySelectorAll('.nav-item').forEach(n=>n.classList.toggle('active',n.dataset.page===p));
        document.querySelectorAll('.page').forEach(pg=>pg.classList.remove('active'));
        document.getElementById(p).classList.add('active');
        closeAllDropdowns();
        if(p==='pageOrder')renderOrder();
    }

    function toggleTheme(){
        state.dark=!state.dark;
        document.documentElement.classList.toggle('dark',state.dark);
        document.getElementById('themeIcon').className=state.dark?'fas fa-sun':'fas fa-moon';
    }

    function toggleDropdown(id){
        const dd=document.getElementById(id);
        const isOpen=dd.classList.contains('open');
        closeAllDropdowns();
        if(!isOpen){dd.classList.add('open');state.openDropdown=id;}
    }
    function closeAllDropdowns(){document.querySelectorAll('.dropdown').forEach(d=>d.classList.remove('open'));state.openDropdown=null;}
    document.addEventListener('click',e=>{if(state.openDropdown&&!e.target.closest('.header-btn')&&!e.target.closest('.dropdown'))closeAllDropdowns();});

    function setLang(lang){
        state.lang=lang;
        document.documentElement.lang=lang;
        document.documentElement.dir=lang==='en'?'ltr':'rtl';
        document.querySelectorAll('[data-i18n]').forEach(el=>{const k=el.dataset.i18n;if(i18n[lang][k])el.textContent=i18n[lang][k];});
        document.querySelectorAll('#langDropdown .dropdown-item').forEach(it=>it.classList.toggle('active',it.dataset.lang===lang));
        closeAllDropdowns();renderTables();renderOrder();renderGallery();
    }

    function showToast(msg){
        const c=document.getElementById('toastContainer');
        const t=document.createElement('div');t.className='toast';t.textContent=msg;c.appendChild(t);
        setTimeout(()=>{t.classList.add('out');setTimeout(()=>t.remove(),350);},2000);
    }

    function formatNum(n){return n.toLocaleString();}
    function t(k){return i18n[state.lang][k]||k;}

    function renderTables(){
        const g=document.getElementById('tablesGrid');let h='';
        for(let i=1;i<=15;i++){
            h+=`<button class="table-card liquid-glass ${state.selectedTable===i?'selected':''}" onclick="selectTable(${i})" style="animation-delay:${i*0.04}s"><i class="fas fa-chair"></i><span>${t('tablePrefix')} ${i}</span></button>`;
        }
        g.innerHTML=h;
    }

    function selectTable(n){state.selectedTable=n;renderTables();showToast(`${t('tablePrefix')} ${n}`);setTimeout(()=>navigateTo('pageOrder'),400);}

    function openItemModal(id){
        let f=null;for(const c of Object.values(menuData)){f=c.find(i=>i.id===id);if(f)break;}
        if(!f)return;state.modalItem=f;
        document.getElementById('modalImg').src=f.img;
        document.getElementById('modalName').textContent=f.name[state.lang];
        document.getElementById('modalPrice').textContent=formatNum(f.price)+' '+t('dinar');
        document.getElementById('itemModal').classList.add('open');
    }
    function closeModal(e){if(e&&e.target!==e.currentTarget)return;document.getElementById('itemModal').classList.remove('open');state.modalItem=null;}
    function addItemFromModal(){if(!state.modalItem)return;addToCart(state.modalItem);closeModal({target:document.getElementById('itemModal'),currentTarget:document.getElementById('itemModal')});}

    function addToCart(item){
        const ex=state.cart.find(c=>c.item.id===item.id);
        if(ex){ex.qty++;}else{state.cart.push({item,qty:1});}
        updateCartBadge();renderOrder();showToast(t('added')+' ✓');
    }
    function changeQty(id,d){
        const idx=state.cart.findIndex(c=>c.item.id===id);if(idx===-1)return;
        state.cart[idx].qty+=d;
        if(state.cart[idx].qty<=0){state.cart.splice(idx,1);showToast(t('removed')+' ✕');}
        updateCartBadge();renderOrder();
    }
    function removeFromCart(id){state.cart=state.cart.filter(c=>c.item.id!==id);updateCartBadge();renderOrder();showToast(t('removed')+' ✕');}
    function updateCartBadge(){const b=document.getElementById('cartBadge');const c=state.cart.reduce((s,x)=>s+x.qty,0);b.textContent=c;b.classList.toggle('show',c>0);}

    function renderOrder(){
        const ct=document.getElementById('orderContent');
        const bd=document.getElementById('orderTableBadge');
        const tn=document.getElementById('orderTableName');
        if(state.selectedTable){bd.style.display='inline-flex';tn.textContent=`${t('tablePrefix')} ${state.selectedTable}`;}else{bd.style.display='none';}

        if(state.cart.length===0){
            let h=`<div class="order-empty"><i class="fas fa-shopping-bag"></i><p style="font-weight:700;margin-bottom:4px;">${t('orderEmpty')}</p><p style="font-size:.8rem;">${t('orderEmptySub')}</p></div>`;
            h+=renderMenuTabs();h+=renderMenuGrid();ct.innerHTML=h;return;
        }

        let h='';
        state.cart.forEach((c,i)=>{
            h+=`<div class="order-item" style="animation-delay:${i*0.05}s">
                <img class="order-item-img" src="${c.item.img}" alt="" loading="lazy">
                <div class="order-item-info">
                    <div class="order-item-name">${c.item.name[state.lang]}</div>
                    <div class="order-item-price">${formatNum(c.item.price*c.qty)} ${t('dinar')}</div>
                </div>
                <div class="order-item-controls">
                    <button class="qty-btn remove" onclick="removeFromCart('${c.item.id}')"><i class="fas fa-trash-alt" style="font-size:.7rem;"></i></button>
                    <button class="qty-btn" onclick="changeQty('${c.item.id}',-1)">−</button>
                    <span class="qty-num">${c.qty}</span>
                    <button class="qty-btn" onclick="changeQty('${c.item.id}',1)">+</button>
                </div>
            </div>`;
        });

        const total=state.cart.reduce((s,c)=>s+c.item.price*c.qty,0);
        h+=`<div class="order-total"><span class="order-total-label">${t('total')}</span><span class="order-total-value">${formatNum(total)} ${t('dinar')}</span></div>`;
        h+=`<button class="send-btn" onclick="sendOrder()" ${!state.selectedTable?'disabled':''}><i class="fab fa-whatsapp" style="margin-left:8px;font-size:1.2rem;"></i>${t('send')}</button>`;
        if(!state.selectedTable)h+=`<p style="text-align:center;color:var(--danger);font-size:.78rem;margin-top:8px;font-weight:600;">${t('selectTableFirst')}</p>`;

        h+=`<div style="margin-top:20px;"><p style="font-weight:700;margin-bottom:10px;font-size:.9rem;color:var(--muted);">${t('addMore')}</p>`;
        h+=renderMenuTabs();h+=renderMenuGrid();h+='</div>';
        ct.innerHTML=h;
    }

    function renderMenuTabs(){
        const cats=['cake','sweets','coffee','cold'];
        let h='<div class="menu-tabs">';
        cats.forEach(c=>{h+=`<button class="menu-tab ${activeMenuCat===c?'active':''}" onclick="switchMenuCat('${c}')">${t(c)}</button>`;});
        h+='</div>';return h;
    }
    function switchMenuCat(c){activeMenuCat=c;renderOrder();}

    function renderMenuGrid(){
        const items=menuData[activeMenuCat]||[];
        let h='<div class="menu-grid">';
        items.forEach((item,i)=>{
            h+=`<div class="menu-card" onclick="openItemModal('${item.id}')" style="animation-delay:${i*0.06}s">
                <div class="menu-card-img-wrap"><img class="menu-card-img" src="${item.img}" alt="" loading="lazy"></div>
                <div class="menu-card-body"><div class="menu-card-name">${item.name[state.lang]}</div><div class="menu-card-price">${formatNum(item.price)} ${t('dinar')}</div></div>
            </div>`;
        });
        h+='</div>';return h;
    }

    function sendOrder(){
        if(!state.selectedTable){showToast(t('selectTableFirst'));return;}
        if(state.cart.length===0)return;
        let msg=`☕ *Calista Bakery*\n🪑 ${t('tablePrefix')}: ${state.selectedTable}\n━━━━━━━━━━━━━\n`;
        let total=0;
        state.cart.forEach(c=>{const sub=c.item.price*c.qty;total+=sub;msg+=`📦 ${c.item.name[state.lang]}\n   ${t('items')}: ${c.qty} × ${formatNum(c.item.price)} = ${formatNum(sub)} ${t('dinar')}\n\n`;});
        msg+=`━━━━━━━━━━━━━\n💰 ${t('total')}: *${formatNum(total)} ${t('dinar')}*`;
        window.open(`https://wa.me/9647505850338?text=${encodeURIComponent(msg)}`,'_blank');
        showToast(t('orderSent'));state.cart=[];updateCartBadge();renderOrder();
    }

    function renderGallery(){
        const g=document.getElementById('galleryGrid');let h='';
        galleryImages.forEach((img,i)=>{
            h+=`<div class="gallery-item ${img.span?'span-2':''}" style="animation-delay:${i*0.06}s">
                <img src="${img.img}" alt="Calista Bakery" loading="lazy" onclick="openGalleryModal('${img.img}')">
                <button class="gallery-dl-btn" id="gdl${i}" onclick="event.stopPropagation();downloadFromGrid('${img.img}','gdl${i}')">
                    <i class="fas fa-download"></i><span>${t('downloadHQ')}</span>
                </button>
            </div>`;
        });
        g.innerHTML=h;
    }

    async function downloadFromGrid(url,btnId){
        const btn=document.getElementById(btnId);if(!btn||btn.classList.contains('downloading'))return;
        btn.classList.add('downloading');const orig=btn.innerHTML;btn.innerHTML=`<i class="fas fa-spinner fa-spin"></i><span>${t('downloading')}</span>`;
        try{await downloadImage(url);showToast(t('downloadHQ')+' ✓');}catch(e){showToast('Error');}
        setTimeout(()=>{btn.classList.remove('downloading');btn.innerHTML=orig;},1500);
    }

    function openGalleryModal(url){state.galleryModalSrc=url;document.getElementById('galleryModalImg').src=url;document.getElementById('galleryModal').classList.add('open');const d=document.getElementById('galleryModalDl');d.classList.remove('downloading');d.innerHTML=`<i class="fas fa-download"></i><span>${t('downloadHQ')}</span>`;}
    function closeGalleryModal(){document.getElementById('galleryModal').classList.remove('open');state.galleryModalSrc=null;}

    async function downloadGalleryImage(){
        const d=document.getElementById('galleryModalDl');if(d.classList.contains('downloading')||!state.galleryModalSrc)return;
        d.classList.add('downloading');d.innerHTML=`<i class="fas fa-spinner fa-spin"></i><span>${t('downloading')}</span>`;
        try{await downloadImage(state.galleryModalSrc);showToast(t('downloadHQ')+' ✓');}catch(e){showToast('Error');}
        setTimeout(()=>{d.classList.remove('downloading');d.innerHTML=`<i class="fas fa-download"></i><span>${t('downloadHQ')}</span>`;},1500);
    }

    async function downloadImage(url){
        try{const r=await fetch(url);if(!r.ok)throw 0;const b=await r.blob();const u=URL.createObjectURL(b);triggerDL(u,'calista_bakery_'+Date.now()+'.jpg');setTimeout(()=>URL.revokeObjectURL(u),10000);return;}catch(e){}
        try{const img=new Image();img.crossOrigin='anonymous';await new Promise((res,rej)=>{img.onload=res;img.onerror=rej;img.src=url;});const cv=document.createElement('canvas');cv.width=img.naturalWidth;cv.height=img.naturalHeight;cv.getContext('2d').drawImage(img,0,0);const b=await new Promise(r=>cv.toBlob(r,'image/jpeg',1));const u=URL.createObjectURL(b);triggerDL(u,'calista_bakery_'+Date.now()+'.jpg');setTimeout(()=>URL.revokeObjectURL(u),10000);return;}catch(e){}
        window.open(url,'_blank');
    }

    function triggerDL(url,name){const a=document.createElement('a');a.href=url;a.download=name;a.style.display='none';document.body.appendChild(a);a.click();document.body.removeChild(a);}

    document.getElementById('galleryModal').addEventListener('click',function(e){if(e.target===this)closeGalleryModal();});

    renderTables();renderOrder();renderGallery();
    </script>
</body>
</html>
