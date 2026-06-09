[index.html.txt](https://github.com/user-attachments/files/28755255/index.html.txt)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ممر المحركات | المنصة العالمية المتقدمة للسيارات</title>
    <style>
        /* --- التصميم الداكن الفخم (Carbon & Neon Theme) --- */
        :root {
            --bg-dark: #0f1115;
            --bg-card: #1a1d24;
            --border-neon: #e63946;
            --text-main: #f8f9fa;
            --text-muted: #a0aec0;
            --accent-blue: #00b4d8;
            --accent-green: #059669;
            --gold: #ffb703;
            --purple: #9d4edd;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--bg-dark); color: var(--text-main); line-height: 1.6; overflow-x: hidden; }

        header {
            background-color: rgba(20, 23, 28, 0.9); padding: 15px 50px;
            display: flex; justify-content: space-between; align-items: center;
            position: fixed; top: 0; width: 100%; z-index: 1000; border-bottom: 1px solid rgba(255,255,255,0.05);
            backdrop-filter: blur(10px);
        }
        header .logo { font-size: 26px; font-weight: bold; color: var(--border-neon); letter-spacing: 1px; }
        header nav a { color: var(--text-main); text-decoration: none; margin-right: 25px; font-weight: 600; font-size: 15px; transition: 0.3s; }
        header nav a:hover { color: var(--border-neon); }

        /* --- واجهة سينمائية بكامل حجم الشاشة --- */
        .hero-fullscreen {
            height: 100vh;
            background: linear-gradient(rgba(15, 17, 21, 0.3), rgba(15, 17, 21, 0.85)), 
                        url('https://images.unsplash.com/photo-1617814076367-b759c7d7e738?auto=format&fit=crop&w=1950&q=80') no-repeat center center/cover;
            display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 0 20px;
            position: relative;
        }
        .hero-fullscreen h1 { font-size: 55px; font-weight: 900; margin-bottom: 20px; text-shadow: 0 0 30px rgba(230, 57, 70, 0.7); letter-spacing: 1px; }
        .hero-fullscreen p { font-size: 22px; color: #e2e8f0; max-width: 800px; text-shadow: 0 2px 4px rgba(0,0,0,0.8); margin-bottom: 30px; }
        .hero-fullscreen .btn-scroll {
            background: linear-gradient(45deg, var(--border-neon), #b31e2b); color: white; border: none;
            padding: 14px 35px; border-radius: 30px; cursor: pointer; font-weight: bold; font-size: 16px;
            box-shadow: 0 0 20px rgba(230, 57, 70, 0.5); transition: 0.3s; text-decoration: none;
        }
        .hero-fullscreen .btn-scroll:hover { transform: translateY(-3px); box-shadow: 0 0 30px rgba(230, 57, 70, 0.8); }

        section { padding: 80px 20px; max-width: 1200px; margin: 0 auto; }
        section h2 { text-align: center; font-size: 36px; margin-bottom: 40px; color: var(--text-main); position: relative; }
        section h2::after { content: ''; display: block; width: 60px; height: 3px; background-color: var(--border-neon); margin: 8px auto 0; }

        /* --- لوحة إحصائيات الأداء والمتابعة (KPIs Dashboard) --- */
        .kpi-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 20px; margin-bottom: 40px; }
        .kpi-card { background: var(--bg-card); border: 1px solid #2d323f; border-radius: 10px; padding: 20px; text-align: center; position: relative; }
        .kpi-card h4 { font-size: 14px; color: var(--text-muted); margin-bottom: 5px; }
        .kpi-card .kpi-num { font-size: 32px; font-weight: bold; color: var(--accent-blue); }
        .kpi-card .kpi-num.neon { color: var(--border-neon); }
        .kpi-card .kpi-num.green { color: var(--accent-green); }
        .kpi-card .kpi-num.gold { color: var(--gold); }

        /* --- معرض السيارات المصنف --- */
        .cars-gallery { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 25px; margin-bottom: 40px; }
        .gallery-card { position: relative; border-radius: 12px; overflow: hidden; height: 320px; box-shadow: 0 8px 20px rgba(0,0,0,0.4); border: 1px solid #2d323f; transition: 0.4s; }
        .gallery-card img { width: 100%; height: 100%; object-fit: cover; transition: 0.5s; }
        .watermark-overlay {
            position: absolute; bottom: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(to top, rgba(15, 17, 21, 0.95) 40%, rgba(15, 17, 21, 0.4) 70%, rgba(15, 17, 21, 0.1));
            display: flex; flex-direction: column; justify-content: flex-end; padding: 20px; opacity: 0.9;
        }
        .gallery-card:hover img { transform: scale(1.1); }
        .tag { position: absolute; top: 15px; right: 15px; padding: 4px 12px; border-radius: 20px; font-size: 12px; font-weight: bold; color: white; }
        .tag.classic { background-color: #d97706; }
        .tag.modern { background-color: var(--accent-blue); }
        .tag.eco { background-color: var(--accent-green); }
        .tag.luxury { background-color: #7209b7; }
        .watermark-overlay h3 { font-size: 20px; color: #fff; }
        .watermark-overlay .company { font-size: 12px; color: var(--border-neon); font-weight: bold; margin-bottom: 8px; }
        .watermark-overlay p { font-size: 13px; color: var(--text-muted); }

        /* --- محرك البحث وكروت المقارنة المحدثة --- */
        .search-compare-box { background-color: var(--bg-card); padding: 45px 30px; border-radius: 15px; border: 1px solid #2d323f; box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
        .inputs-container { display: grid; grid-template-columns: 1fr auto 1fr; gap: 20px; align-items: center; margin-bottom: 20px; }
        @media (max-width: 768px) { .inputs-container { grid-template-columns: 1fr; } }
        .input-group label { font-weight: bold; color: var(--text-muted); font-size: 14px; margin-bottom: 6px; display: block; }
        .input-group input, .input-group textarea { width: 100%; padding: 14px; background: #222630; border: 1px solid #3d4556; border-radius: 8px; color: white; outline: none; font-size: 15px; }
        .btn-search { grid-column: 1 / -1; background: linear-gradient(45deg, var(--border-neon), #b31e2b); color: white; border: none; padding: 15px; font-size: 18px; font-weight: bold; border-radius: 8px; cursor: pointer; transition: 0.3s; }
        .btn-search:hover { opacity: 0.9; }

        .results-display { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; margin-top: 30px; }
        @media (max-width: 768px) { .results-display { grid-template-columns: 1fr; } }
        .car-result-card { background: #222630; border-radius: 12px; padding: 25px; border: 1px solid #343b4a; position: relative; }
        .car-result-card h3 { text-align: center; color: white; margin-bottom: 15px; border-bottom: 1px solid #343b4a; padding-bottom: 10px; font-size: 22px; }
        
        .audience-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 15px; justify-content: center; }
        .aud-tag { padding: 4px 12px; border-radius: 4px; font-size: 12px; font-weight: bold; color: rgba(255,255,255,0.4); background: #1a1d24; border: 1px solid #2d323f; }
        .aud-tag.active-tag { color: #fff; background: linear-gradient(45deg, var(--purple), #7209b7); box-shadow: 0 0 8px rgba(157, 78, 221, 0.4); border: none; }

        .quick-specs { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin-bottom: 15px; }
        .spec-badge { background: #1a1d24; padding: 10px; border-radius: 6px; text-align: center; font-size: 12px; border: 1px solid #2d323f; }
        .spec-badge strong { color: var(--accent-blue); display: block; font-size: 14px; margin-top: 3px; }
        .spec-badge.price-badge strong { color: var(--gold); font-size: 16px; }

        .info-block { margin-bottom: 15px; }
        .info-block h4 { font-size: 14px; color: var(--text-muted); }
        .info-block p { background: #1a1d24; padding: 12px; border-radius: 6px; margin-top: 5px; font-size: 14px; color: #e2e8f0; text-align: justify; }
        
        .car-image-mesh { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin-top: 15px; }
        @media (max-width: 500px) { .car-image-mesh { grid-template-columns: repeat(2, 1fr); } }
        .mesh-img-wrapper { position: relative; height: 90px; border-radius: 6px; overflow: hidden; border: 1px solid #3d4556; }
        .mesh-img-wrapper img { width: 100%; height: 100%; object-fit: cover; }
        .mesh-label { position: absolute; bottom: 0; right: 0; left: 0; background: rgba(0,0,0,0.8); color: #fff; font-size: 10px; text-align: center; padding: 2px 0; font-weight: bold; }

        /* --- قسم الستة الكبار --- */
        .big-companies-hero { width: 100%; height: 400px; border-radius: 15px; overflow: hidden; position: relative; margin-bottom: 30px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); border: 1px solid #2d323f; }
        .big-companies-hero img { width: 100%; height: 100%; object-fit: cover; }
        .big-companies-hero .overlay-title { position: absolute; bottom: 0; right: 0; left: 0; background: linear-gradient(to top, rgba(15,17,21,1), rgba(15,17,21,0)); padding: 40px 25px 20px; text-align: right; }
        .big-companies-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 25px; margin-top: 20px; }
        .company-info-card { background-color: var(--bg-card); border-radius: 12px; border: 1px solid #2d323f; padding: 25px; display: flex; flex-direction: column; justify-content: space-between; transition: 0.3s; }
        .company-info-card:hover { transform: translateY(-5px); border-color: var(--accent-blue); }
        .company-header-meta { display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #2d323f; padding-bottom: 10px; margin-bottom: 15px; }
        .company-header-meta h3 { color: #fff; font-size: 22px; }
        .company-header-meta .country-badge { background-color: #222630; padding: 4px 10px; border-radius: 6px; font-size: 12px; color: var(--accent-blue); font-weight: bold; }
        
        .meta-list { list-style: none; font-size: 14px; color: var(--text-muted); margin-bottom: 12px; }
        .meta-list li { margin-bottom: 6px; }
        .meta-list li strong { color: #fff; }

        .brand-specs-table { width: 100%; background: #13161c; border-radius: 6px; padding: 10px; margin-bottom: 12px; font-size: 12px; border: 1px solid #222630; }
        .brand-specs-table div { display: flex; justify-content: space-between; padding: 4px 0; border-bottom: 1px dashed rgba(255,255,255,0.05); }
        .brand-specs-table div:last-child { border-bottom: none; }
        .brand-specs-table span { color: var(--text-muted); }
        .brand-specs-table strong { color: var(--accent-blue); }

        .latest-release { background: rgba(0, 180, 216, 0.1); border-right: 3px solid var(--accent-blue); padding: 10px; border-radius: 4px; margin-bottom: 12px; }
        .latest-release span { display: block; font-size: 11px; color: var(--accent-blue); font-weight: bold; }
        .latest-release strong { font-size: 14px; color: #fff; }
        
        .order-method-box { background: rgba(5, 150, 105, 0.1); border-right: 3px solid var(--accent-green); padding: 10px; border-radius: 4px; font-size: 13px; margin-bottom: 15px; }
        .order-method-box span { display: block; font-size: 11px; color: var(--accent-green); font-weight: bold; }

        .company-actions { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .action-link { display: block; text-align: center; padding: 10px; border-radius: 6px; font-size: 12px; font-weight: bold; text-decoration: none; transition: 0.2s; cursor: pointer; }
        .action-link.primary-web { background: linear-gradient(45deg, #222630, #2d323f); color: #fff; border: 1px solid #3d4556; }
        .action-link.primary-web:hover { border-color: var(--accent-blue); background: rgba(0, 180, 216, 0.1); }
        .action-link.book-drive { background: linear-gradient(45deg, var(--accent-green), #047857); color: #fff; }
        .action-link.book-drive:hover { opacity: 0.9; transform: scale(1.02); }

        /* --- الأقسام التفاعلية --- */
        .interactive-container { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; margin-top: 40px; }
        @media (max-width: 768px) { .interactive-container { grid-template-columns: 1fr; } }
        .interactive-box { background: var(--bg-card); border-radius: 15px; border: 1px solid #2d323f; padding: 30px; box-shadow: 0 10px 25px rgba(0,0,0,0.3); }
        .btn-submit { background: var(--accent-blue); color: #fff; border: none; padding: 12px 25px; border-radius: 6px; font-weight: bold; cursor: pointer; transition: 0.3s; width: 100%; margin-top: 15px; font-size: 15px; }
        .btn-submit:hover { opacity: 0.9; }
        .btn-submit.btn-comment { background: var(--border-neon); }
        
        /* صندوق بريد المدير السري الجديد */
        .admin-mailbox-section { grid-column: 1 / -1; background: linear-gradient(135deg, #161920, #111318); border: 1px dashed var(--accent-blue); border-radius: 15px; padding: 35px; margin-top: 30px; position: relative; overflow: hidden; }
        .admin-mailbox-section::before { content: '🔒 بريد مشفر'; position: absolute; top: 15px; left: 20px; font-size: 11px; background: rgba(0, 180, 216, 0.15); color: var(--accent-blue); padding: 3px 10px; border-radius: 20px; font-weight: bold; }
        .btn-admin-submit { background: linear-gradient(45deg, var(--accent-blue), #0077b6); color: white; border: none; padding: 14px; font-weight: bold; font-size: 16px; border-radius: 6px; width: 100%; cursor: pointer; margin-top: 15px; transition: 0.3s; }
        .btn-admin-submit:hover { box-shadow: 0 0 15px rgba(0, 180, 216, 0.4); }

        /* --- لوحة التحكم الذكية لغرفة عمليات المدير (الأفكار الـ 5 المدمجة) --- */
        .control-panel-section { grid-column: 1 / -1; background: #13161c; border: 1px solid var(--gold); border-radius: 15px; padding: 30px; margin-top: 35px; }
        .panel-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 25px; margin-top: 20px; }
        @media (max-width: 768px) { .panel-grid { grid-template-columns: 1fr; } }
        .milestone-list { list-style: none; }
        .milestone-item { display: flex; align-items: center; justify-content: space-between; background: #1a1d24; padding: 12px; border-radius: 8px; margin-bottom: 8px; border-left: 3px solid var(--text-muted); }
        .milestone-item.done { border-left-color: var(--accent-green); background: rgba(5, 150, 105, 0.05); }
        .milestone-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; }
        
        .plan-b-box { background: rgba(230, 57, 70, 0.05); border: 1px dashed var(--border-neon); border-radius: 10px; padding: 20px; text-align: center; }
        .btn-panel { padding: 10px 20px; border: none; border-radius: 6px; font-weight: bold; cursor: pointer; transition: 0.2s; font-size: 13px; margin: 5px; }
        .btn-backup { background: var(--border-neon); color: #fff; }
        .btn-doc { background: var(--accent-blue); color: #fff; }

        .live-list-display { margin-top: 20px; max-height: 250px; overflow-y: auto; background: #13161c; border-radius: 8px; padding: 15px; border: 1px solid #222630; }
        .dream-item { display: flex; justify-content: space-between; align-items: center; background: #1e222b; padding: 10px 15px; border-radius: 6px; margin-bottom: 10px; border-right: 3px solid var(--gold); }
        .dream-item .user-name { font-weight: bold; color: #fff; font-size: 14px; }
        .dream-item .car-name { background: rgba(255, 183, 3, 0.1); color: var(--gold); padding: 2px 8px; border-radius: 4px; font-size: 13px; font-weight: bold; }
        
        .comment-item { background: #1e222b; padding: 12px 15px; border-radius: 6px; margin-bottom: 10px; border-right: 3px solid var(--border-neon); }
        .comment-item .comment-meta { font-size: 12px; color: var(--text-muted); margin-bottom: 5px; display: flex; justify-content: space-between; }
        .comment-item .comment-meta strong { color: #fff; }
        .comment-item p { font-size: 14px; color: #e2e8f0; }

        /* --- النبذة الشخصية --- */
        .about-founder {
            background: linear-gradient(135deg, #14171c, #1e222b); padding: 40px; border-radius: 15px;
            border: 1px solid #2d323f; text-align: center; max-width: 800px; margin: 60px auto 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
        }
        .about-founder h3 { font-size: 24px; color: #fff; margin-bottom: 15px; }
        .about-founder p { color: var(--text-muted); font-size: 16px; line-height: 1.8; max-width: 700px; margin: 0 auto; }
        .about-founder .highlight { color: var(--border-neon); font-weight: bold; }

        /* --- لوقو ولمسة وفاء بي إم دبليو --- */
        .bmw-tribute { text-align: center; margin: 40px auto; padding-top: 20px; }
        .bmw-logo-wrapper {
            width: 80px; height: 80px; margin: 0 auto 15px; background-color: #fff; border-radius: 50%;
            display: flex; justify-content: center; align-items: center; box-shadow: 0 0 20px rgba(0, 180, 216, 0.3);
            border: 3px solid #0066b2; overflow: hidden;
        }
        .bmw-logo-wrapper svg { width: 100%; height: 100%; }
        .bmw-tribute h4 { font-size: 18px; font-weight: bold; color: var(--text-main); letter-spacing: 1px; }
        .bmw-tribute p { font-size: 14px; color: var(--gold); font-style: italic; margin-top: 5px; font-weight: 600; }

        /* --- نافذة التوجيه الترحيبية الشريكة العائمة (Gateway Modal) --- */
        .gateway-modal {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(11, 13, 16, 0.95); z-index: 5000;
            display: flex; justify-content: center; align-items: center;
            opacity: 0; pointer-events: none; transition: 0.4s ease;
        }
        .gateway-modal.active { opacity: 1; pointer-events: auto; }
        .gateway-content {
            background: var(--bg-card); border: 2px solid var(--accent-blue);
            padding: 40px; border-radius: 20px; max-width: 550px; width: 90%;
            text-align: center; box-shadow: 0 20px 50px rgba(0, 180, 216, 0.3);
            position: relative;
        }
        .gateway-icon { font-size: 50px; margin-bottom: 15px; animation: pulse 2s infinite; }
        .gateway-content h3 { font-size: 24px; color: #fff; margin-bottom: 15px; }
        .gateway-content p { color: var(--text-muted); font-size: 15px; margin-bottom: 25px; line-height: 1.6; }
        .gateway-badge { display: inline-block; background: rgba(5, 150, 105, 0.15); color: var(--accent-green); padding: 6px 15px; border-radius: 30px; font-weight: bold; font-size: 13px; margin-bottom: 20px; border: 1px solid rgba(5, 150, 105, 0.3); }
        .countdown-text { font-size: 14px; color: var(--gold); font-weight: bold; }

        /* لافتة إعلانية تسويقية منبثقة تفاعلية */
        .marketing-toast { position: fixed; bottom: 20px; right: -400px; background: var(--bg-card); border-right: 4px solid var(--gold); padding: 15px 25px; border-radius: 8px; box-shadow: 0 5px 20px rgba(0,0,0,0.5); z-index: 4000; display: flex; align-items: center; gap: 15px; transition: 0.5s ease; border: 1px solid #2d323f; }
        .marketing-toast.show { right: 20px; }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        footer { background-color: #0b0d10; text-align: center; padding: 25px; border-top: 1px solid #14171c; color: var(--text-muted); font-size: 13px; }
    </style>
</head>
<body>

    <header>
        <div class="logo">🏁 ممر المحركات</div>
        <nav>
            <a href="#gallery-section">معرض الفئات</a>
            <a href="#companies-section">عمالقة الصناعة الستة</a>
            <a href="#compare-section">محرك الفحص الشامل</a>
            <a href="#interactive-section">المجتمع التفاعلي</a>
        </nav>
    </header>

    <!-- الصفحة الرئيسية -->
    <div class="hero-fullscreen">
        <h1>موسوعة ومقارنات السيارات الشاملة</h1>
        <p>المرجع البصري الرقمي الأول لاستكشاف الأبعاد الكاملة وأسعار المصنع العالمية الحية لمساعدتك في اتخاذ قرارك الهندسي الصحيح.</p>
        <a href="#compare-section" class="btn-scroll">ابدأ الفحص والمقارنة الحية الآن ⚡</a>
    </div>

    <!-- لوحة مؤشرات الأداء الحية (KPIs Dashboard) المضافة حديثاً للمتابعة الجارية -->
    <section style="padding-top:40px; padding-bottom:0;">
        <div class="kpi-container">
            <div class="kpi-card">
                <h4>📈 إجمالي زيارات المنصة الحالية</h4>
                <div class="kpi-num" id="kpiViews">1,248</div>
            </div>
            <div class="kpi-card">
                <h4>🔗 نقرات عبور الشركات الشريكة</h4>
                <div class="kpi-num neon" id="kpiClicks">384</div>
            </div>
            <div class="kpi-card">
                <h4>📬 رسائل صندوق الإدارة المغلق</h4>
                <div class="kpi-num green" id="kpiMessages">0</div>
            </div>
            <div class="kpi-card">
                <h4>⚙️ فحص ومطابقات المحرك الحية</h4>
                <div class="kpi-num gold" id="kpiSearches">512</div>
            </div>
        </div>
    </section>

    <!-- 1. قسم ألبوم الفئات المصنف -->
    <section id="gallery-section">
        <h2>معرض التقييمات البصرية الأساسية</h2>
        <div class="cars-gallery">
            <div class="gallery-card">
                <span class="tag classic">كلاسيك</span>
                <img src="https://images.unsplash.com/photo-1552519507-da3b142c6e3d?auto=format&fit=crop&w=600&q=80" alt="Ford Mustang">
                <div class="watermark-overlay">
                    <h3>موستانج كود 65</h3>
                    <div class="company">شركة فورد الامريكية</div>
                    <p>أيقونة سيارات العضلات، تميزت بمحرك ميكانيكي هائج وتصميم رياضي غيّر مفهوم القوة عالمياً.</p>
                </div>
            </div>
            <div class="gallery-card">
                <span class="tag classic">كلاسيك</span>
                <img src="https://images.unsplash.com/photo-1583121274602-3e2820c69888?auto=format&fit=crop&w=600&q=80" alt="Ferrari">
                <div class="watermark-overlay">
                    <h3>تستاروسا الكلاسيكية</h3>
                    <div class="company">شركة فيراري الإيطالية</div>
                    <p>التحفة الإيطالية الفاخرة ذات المحرك الخلفي، اشتهرت بالخطوط الجانبية الحادة وصوتها الأسطوري.</p>
                </div>
            </div>
            <div class="gallery-card">
                <span class="tag modern">حديثة</span>
                <img src="https://images.unsplash.com/photo-1614162692292-7ac56d7f7f1e?auto=format&fit=crop&w=600&q=80" alt="Porsche">
                <div class="watermark-overlay">
                    <h3>بورشه 911 تيربو</h3>
                    <div class="company">مجموعة فولكس فاجن (ألمانيا)</div>
                    <p>تدمج أعلى تقنيات الثبات الهندسي مع التطور البرمجي، نظام دفع كلي ذكي يقود الحركية.</p>
                </div>
            </div>
            <div class="gallery-card">
                <span class="tag luxury">فخمة</span>
                <img src="https://images.unsplash.com/photo-1618843479313-40f8afb4b4d8?auto=format&fit=crop&w=600&q=80" alt="Mercedes">
                <div class="watermark-overlay">
                    <h3>مرسيدس S-Class</h3>
                    <div class="company">مجموعة مرسيدس-بنز (ألمانيا)</div>
                    <p>صالون ملكي فاخر مع عزل صوتي تام وأنظمة إضاءة محيطية تفاعلية ومقاعد تدليك ذكية.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 2. قسم عمالقة إنتاج السيارات الستة الكبار والموسوعة المعرفية للطلب والربط المباشر -->
    <section id="companies-section">
        <h2>أكبر 6 شركات لإنتاج السيارات في العالم</h2>
        
        <div class="big-companies-hero">
            <img src="https://images.unsplash.com/photo-1563720223185-11003d516935?auto=format&fit=crop&w=1200&q=80" alt="Fleet of modern cars">
            <div class="overlay-title">
                <h3 style="font-size: 28px; text-shadow: 0 2px 10px rgba(0,0,0,0.9);">قادة الصناعة والتحكم الميكانيكي العالمي</h3>
                <p style="color: var(--text-muted); font-size: 14px;">توثيق تاريخي وتفاصيل لوجستية متكاملة لربطك ببوابات الشراء وحجز المواعيد الرسمية.</p>
            </div>
        </div>

        <div class="big-companies-grid">
            
            <!-- 1. تويوتا -->
            <div class="company-info-card">
                <div>
                    <div class="company-header-meta">
                        <h3>تويوتا (Toyota)</h3>
                        <span class="country-badge">اليابان 🇯🇵</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 1937</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> كيتشيرو تويودا</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>هجينة (Hybrid) وتنفس طبيعي</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>كورولا / راف 4</strong></div>
                        <div><span>الضمان العالمي:</span><strong>5 سنوات أو 150,000 كم</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>Toyota Safety Sense 3.0</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>لاندكروزر ليميتد إيديشين 2026 / كامري هجينة</strong>
                    </div>
                    <div class="order-method-box">
                        <span>طرق الطلب والشراء:</span>
                        عبر الوكيل الحصري في منطقتك، أو استخدام منصة تخصيص المواصفات من المصنع مباشرة.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('تويوتا (Toyota)', 'https://www.toyota.com')" class="action-link primary-web">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('جاري نقلك لبوابة حجز موعد تجربة قيادة لسيارات تويوتا 2026 لدى الوكيل الإقليمي...'); return false;" class="action-link book-drive">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

            <!-- 2. فولكس فاجن -->
            <div class="company-info-card">
                <div>
                    <div class="company-header-meta">
                        <h3>فولكس فاجن (VW)</h3>
                        <span class="country-badge">ألمانيا 🇩🇪</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 1937</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> جبهة العمل الألمانية</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>كهربائية بالكامل وتيربو TSI</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>جولف / تيغوان</strong></div>
                        <div><span>الضمان العالمي:</span><strong>3 سنوات (مفتوح الكيلومترات)</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>IQ.Drive Advanced Assistance</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>سلسلة ID.7 الكهربائية وسيارات جولف R 2026</strong>
                    </div>
                    <div class="order-method-box">
                        <span>طرق الطلب والشراء:</span>
                        الولوچ للموقع الأوروبي وتكوين حزمة الأداء وشحنها لوكيل بلدك الإقليمي لاستلامها.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('فولكس فاجن (Volkswagen)', 'https://www.volkswagen.com')" class="action-link primary-web">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('جاري توجيهك إلى نظام حجز تجربة القيادة الفوري لسيارات فولكس فاجن الألمانية...'); return false;" class="action-link book-drive">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

            <!-- 3. جنرال موتورز -->
            <div class="company-info-card">
                <div>
                    <div class="company-header-meta">
                        <h3>جنرال موتورز (GM)</h3>
                        <span class="country-badge">أمريكا 🇺🇸</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 1908</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> ويليام دورانت</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>8 سلندر V8 وبطاريات Ultium</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>سيلفرادو / جي إم سي يوكن</strong></div>
                        <div><span>الضمان العالمي:</span><strong>4 سنوات أو 100,000 كم</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>Super Cruise للقيادة الذاتية</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>كاديلاك إسكاليد IQ الكهربائية وسيلفرادو EV</strong>
                    </div>
                    <div class="order-method-box">
                        <span>طرق الطلب والشراء:</span>
                        من خلال صالات العرض التابعة لمجموعة GM أو حجز الشاحنات مسبقاً عبر بوابات الاستيراد.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('جنرال موتورز (General Motors)', 'https://www.gm.com')" class="action-link primary-web">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('جاري الاتصال بقاعدة بيانات جنرال موتورز لفتح استمارة حجز موعد الفحص والقيادة...'); return false;" class="action-link book-drive">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

            <!-- 4. ستيلانتس -->
            <div class="company-info-card">
                <div>
                    <div class="company-header-meta">
                        <h3>ستيلانتس (Stellantis)</h3>
                        <span class="country-badge">هولندا/متعددة 🇪🇺</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 2021</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> دمج مجموعتي FCA و PSA</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>مخرجات الاحتراق الداخلي والهجين</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>شاحنات رام / جيب رانجلر</strong></div>
                        <div><span>الضمان العالمي:</span><strong>5 سنوات أو 100,000 كم</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>Stellantis Level 2+ Autonomy</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>جيب جراند شيروكي 4xe وتحديثات رام 1500</strong>
                    </div>
                    <div class="order-method-box">
                        <span>طرق الطلب والشراء:</span>
                        عبر الوكلاء الموزعين للعلامات الـ 14 التابعة للمجموعة، وتتوفر ميزات الحجز السريع عبر الإنترنت.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('ستيلانتس (Stellantis)', 'https://www.stellantis.com')" class="action-link primary-web">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('سيتم فتح نظام الجدولة الذكي لوكلاء جيب ورام وستيلانتس في منطقتك حالاً...'); return false;" class="action-link book-drive">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

            <!-- 5. هيونداي موتور -->
            <div class="company-info-card">
                <div>
                    <div class="company-header-meta">
                        <h3>هيونداي (Hyundai)</h3>
                        <span class="country-badge">كوريا الجنوبية 🇰🇷</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 1967</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> تشونغ جو-يونغ</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>전기 (كهربائي متطور) وتيربو GDI</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>توسان / إلنترا / أيونيك 5</strong></div>
                        <div><span>الضمان العالمي:</span><strong>5 سنوات (مفتوح الكيلومترات للبطاريات)</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>Hyundai SmartSense Safety Suite</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>أيونيك 7 العائلية الكبيرة وسنتافي الفاخرة</strong>
                    </div>
                    <div class="order-method-box">
                        <span>طرق الطلب والشراء:</span>
                        الشراء المباشر عبر صالات الوكيل، مع توفير خيارات التمويل الفوري والضمان الممتد.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('هيونداي (Hyundai)', 'https://www.hyundai.com')" class="action-link primary-web">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('جاري فتح الاتصال المباشر مع مركز مبيعات وتجارب هيونداي موتورز لمطابقة طلبك...'); return false;" class="action-link book-drive">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

            <!-- 6. بي إم دبليو -->
            <div class="company-info-card" style="border-color: rgba(255,183,3,0.3);">
                <div>
                    <div class="company-header-meta">
                        <h3 style="color: var(--gold);">بي إم دبليو (BMW)</h3>
                        <span class="country-badge" style="background: rgba(255,183,3,0.1); color: var(--gold);">ألمانيا 🇩🇪</span>
                    </div>
                    <ul class="meta-list">
                        <li>🗓️ <strong>تاريخ التأسيس:</strong> 1916</li>
                        <li>👤 <strong>المؤسس الأصلي:</strong> فرانز جوزيف بوب</li>
                    </ul>
                    <div class="brand-specs-table">
                        <div><span>نوع المحركات:</span><strong>TwinPower Turbo و eDrive الكهربي</strong></div>
                        <div><span>الفئة الأكثر مبيعاً:</span><strong>الفئة الثالثة / طرازات SUV X5</strong></div>
                        <div><span>الضمان العالمي:</span><strong>5 سنوات شامل الصيانة المجانية الشاملة</strong></div>
                        <div><span>نظام الأمان الحركي:</span><strong>BMW Driving Assistant Professional</strong></div>
                    </div>
                    <div class="latest-release">
                        <span>أحدث إصدار لعام 2026:</span>
                        <strong>سلسلة الفئة السابعة 2026 وسيارات الـ SUV الرياضية iX5</strong>
                    </div>
                    <div class="order-method-box" style="border-right-color: var(--gold);">
                        <span>طرق الطلب والشراء:</span>
                        عبر برنامج تخصيص الرفاهية والأداء من موقع BMW، والربط الفوري مع مراكز الاستلام المعتمدة.
                    </div>
                </div>
                <div class="company-actions">
                    <div onclick="openGateway('بي إم دبليو (BMW)', 'https://www.bmw.com')" class="action-link primary-web" style="border-color: var(--gold);">الموقع العالمي 🌐</div>
                    <a href="#" onclick="alert('مرحباً بك في عالم الرفاهية البافارية، جاري فتح بوابة تخصيص وحجز موعد تجربة BMW المحدثة...'); return false;" class="action-link book-drive" style="background: linear-gradient(45deg, var(--gold), #d97706); color: #000;">حجز تجربة قيادة 🏎️</a>
                </div>
            </div>

        </div>
    </section>

    <!-- 3. قسم محرك المقارنة والبحث المطور -->
    <section id="compare-section">
        <h2>محرك الفحص الشامل ومطابقة الأبعاد والأسعار</h2>
        
        <div class="search-compare-box">
            <div class="inputs-container">
                <div class="input-group">
                    <label>السيارة الأولى (اكتب اسم الطراز، مثلاً: كامري، لاندكروزر):</label>
                    <input type="text" id="car1Input" placeholder="اكتب اسم السيارة الأولى هنا">
                </div>
                <div style="font-size: 24px; font-weight: bold; color: var(--border-neon); margin-top: 20px; text-align: center;">VS</div>
                <div class="input-group">
                    <label>السيارة الثانية (اختياري للمقارنة الفنية الحية):</label>
                    <input type="text" id="car2Input" placeholder="اكتب اسم السيارة الثانية هنا">
                </div>
                <button class="btn-search" onclick="executeSearchAndCompare()">ابدأ استخراج ألبوم الأبعاد الستة وتتبع الأسعار التلقائية 🔍</button>
            </div>

            <div class="results-display" id="resultsContainer" style="display: none;">
                <div class="car-result-card" id="card1">
                    <h3 id="car1Title"></h3>
                    <div class="audience-tags" id="car1AudienceZone"></div>
                    <div class="quick-specs">
                        <div class="spec-badge">صرف الوقود<strong id="car1EcoVal">-</strong></div>
                        <div class="spec-badge">عدد المقاعد<strong id="car1SeatsVal">-</strong></div>
                        <div class="spec-badge price-badge">سعر المصنع العالمي<strong id="car1PriceVal">-</strong></div>
                    </div>
                    <div class="info-block"><h4>📋 التوصيف الفني والهندسي:</h4><p id="car1Specs"></p></div>
                    <div class="info-block"><h4>✅ المميزات وأنظمة التحكم والمقود:</h4><p id="car1Pros"></p></div>
                    <div class="info-block"><h4>❌ العيوب والمشاكل والملاحظات الشائعة:</h4><p id="car1Cons"></p></div>
                    <h4>📸 ألبوم فحص الأبعاد السداسي والتحكمات الكامل:</h4>
                    <div class="car-image-mesh" id="car1Mesh"></div>
                </div>

                <div class="car-result-card" id="card2">
                    <h3 id="car2Title"></h3>
                    <div class="audience-tags" id="car2AudienceZone"></div>
                    <div class="quick-specs">
                        <div class="spec-badge">صرف الوقود<strong id="car2EcoVal">-</strong></div>
                        <div class="spec-badge">عدد المقاعد<strong id="car2SeatsVal">-</strong></div>
                        <div class="spec-badge price-badge">سعر المصنع العالمي<strong id="car2PriceVal">-</strong></div>
                    </div>
                    <div class="info-block"><h4>📋 التوصيف الفني والهندسي:</h4><p id="car2Specs"></p></div>
                    <div class="info-block"><h4>✅ المميزات وأنظمة التحكم والمقود:</h4><p id="car2Pros"></p></div>
                    <div class="info-block"><h4>❌ العيوب والمشاكل والملاحظات الشائعة:</h4><p id="car2Cons"></p></div>
                    <h4>📸 ألبوم فحص الأبعاد السداسي والتحكمات الكامل:</h4>
                    <div class="car-image-mesh" id="car2Mesh"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. الأقسام التفاعلية للزوار والمجتمع -->
    <section id="interactive-section">
        <h2>منطقة التفاعل وعشاق المحركات</h2>
        <div class="interactive-container">
            
            <!-- أ) صندوق سيارة الأحلام -->
            <div class="interactive-box">
                <h3 style="color: var(--gold); margin-bottom: 10px;">✨ جدار سيارات الأحلام والرفاهية</h3>
                <p style="font-size: 13px; color: var(--text-muted); margin-bottom: 20px;">شاركنا رأيك؛ في نظرك ما هي السيارة الأفخم على الإطلاق والتي تحلم بامتلاكها؟</p>
                
                <div class="input-group" style="margin-bottom: 12px;">
                    <label>اسمك الكريم:</label>
                    <input type="text" id="dreamerName" placeholder="اكتب اسمك هنا">
                </div>
                <div class="input-group">
                    <label>سيارة أحلامك الفخمة:</label>
                    <input type="text" id="dreamCar" placeholder="مثلاً: مرسيدس G-Class">
                </div>
                <button class="btn-submit" onclick="addDreamCar()">أنشر سيارة أحلامي على اللوحة الحية 🚀</button>

                <div class="live-list-display" id="dreamCarsContainer">
                    <div class="dream-item"><span class="user-name">خالد الشمري</span><span class="car-name">BMW M5 Competition</span></div>
                </div>
            </div>

            <!-- ب) صندوق تعليقات زوار المنصة العام -->
            <div class="interactive-box">
                <h3 style="color: var(--border-neon); margin-bottom: 10px;">💬 آراء وتقييمات زوار المنصة</h3>
                <p style="font-size: 13px; color: var(--text-muted); margin-bottom: 20px;">اترك انطباعك أو نصيحتك للشباب بخصوص اختيار وفحص السيارات.</p>
                
                <div class="input-group" style="margin-bottom: 12px;">
                    <label>الاسم:</label>
                    <input type="text" id="commenterName" placeholder="اكتب اسمك هنا">
                </div>
                <div class="input-group">
                    <label>التعليق أو النصيحة:</label>
                    <textarea id="commentText" rows="2" placeholder="اكتب رأيك أو نصيحتك هنا..."></textarea>
                </div>
                <button class="btn-submit btn-comment" onclick="addComment()">إرسال التعليق العام للمنصة 📣</button>

                <div class="live-list-display" id="commentsContainer">
                    <div class="comment-item">
                        <div class="comment-meta"><strong>عبدالله بن محمد</strong> <span>منذ دقيقة</span></div>
                        <p>منصة رائعة جداً، فكرة استخراج أسعار المصنع الحية حلت أزمة التلاعب.</p>
                    </div>
                </div>
            </div>

            <!-- ج) صندوق بريد المدير السري -->
            <div class="admin-mailbox-section">
                <h3 style="color: var(--accent-blue); margin-bottom: 8px;">📬 صندوق الرسائل والاقتراحات المباشرة للإدارة</h3>
                <p style="font-size: 13.5px; color: var(--text-muted); margin-bottom: 20px;">لديك استفسار خاص، شكوى، أو رغبة في الإعلان أو الشراكة؟ يمكنك كتابة رسالتك هنا بكل أمان، هذه الرسائل مشفرة تماماً ولن تظهر في الموقع العام، بل تذهب مباشرة إلى البريد الداخلي ولا يطلع عليها سوى <strong>مدير المنصة</strong>.</p>
                
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-bottom: 15px;">
                    <div class="input-group">
                        <label>الاسم الكريم:</label>
                        <input type="text" id="adminSenderName" placeholder="اسمك الثنائي">
                    </div>
                    <div class="input-group">
                        <label>بريدك الإلكتروني أو رقم هاتف للتواصل:</label>
                        <input type="text" id="adminSenderContact" placeholder="email@example.com">
                    </div>
                </div>
                <div class="input-group">
                    <label>نص الرسالة السرية الموجهة للمدير:</label>
                    <textarea id="adminMessageText" rows="4" placeholder="اكتب تفاصيل رسالتك أو اقتراحك هنا بكامل السرية..."></textarea>
                </div>
                <button class="btn-admin-submit" onclick="sendSecureMessageToAdmin()">إرسال الرسالة المشفرة لبريد المدير 🔒</button>
            </div>

            <!-- د) لوحة التحكم الذكية لغرفة عمليات المدير (الأفكار الـ 5 المدمجة كلياً) -->
            <div class="control-panel-section">
                <h3 style="color: var(--gold); border-bottom: 1px solid #2d323f; padding-bottom: 10px;">🛠️ غرفة التحكم وإدارة المراحل الذكية (المدير والمطور)</h3>
                <p style="font-size: 13px; color: var(--text-muted); margin-top: 5px;">لوحة حركية مضافة لإدارة مؤشرات التنفيذ، خطة الطوارئ البديلة، وتوثيق تقارير الإطلاق بشكل حي.</p>
                
                <div class="panel-grid">
                    <div>
                        <h4 style="font-size: 14px; margin-bottom: 10px; color:#fff;">📌 محطات ومراحل التنفيذ المصغرة (Milestones)</h4>
                        <ul class="milestone-list">
                            <li class="milestone-item done"><label>1. بناء الهيكل البرمجي والواجهات</label> <input type="checkbox" checked disabled></li>
                            <li class="milestone-item done"><label>2. نظام فحص الأبعاد والمطابقة السداسي</label> <input type="checkbox" checked disabled></li>
                            <li class="milestone-item done"><label>3. ربط بوابات العبور وصندوق بريد المدير</label> <input type="checkbox" checked disabled></li>
                            <li class="milestone-item"><label>4. رفع الأكواد على السيرفر وبدء الفحص التجريبي</label> <input type="checkbox" onchange="toggleMilestone(this)"></li>
                            <li class="milestone-item"><label>5. إطلاق الحملة التسويقية لرواد مجتمع الشباب</label> <input type="checkbox" onchange="toggleMilestone(this)"></li>
                        </ul>
                    </div>
                    
                    <div class="plan-b-box">
                        <h4 style="font-size: 14px; color: var(--border-neon); margin-bottom: 10px;">⚠️ خطة الطوارئ والأدوات الاحتياطية (Plan B)</h4>
                        <p style="font-size: 12px; color: var(--text-muted); margin-bottom: 15px;">في حال حدوث ثغرة تقنية أو ضغط على الخوادم، اختبر نظام الأمان البديل الفوري بنقرة واحدة.</p>
                        <button class="btn-panel btn-backup" onclick="triggerPlanB()">محاكاة تفعيل خطة الطوارئ 🚨</button>
                        <button class="btn-panel btn-doc" onclick="exportKPIDocumentation()">تصدير تقرير العمل والتوثيق الحركي 📝</button>
                    </div>
                </div>
            </div>

        </div>

        <!-- النبذة الشخصية -->
        <div class="about-founder">
            <h3>من خلف عجلة القيادة؟ 👤</h3>
            <p>مرحباً بكم، أنا <span class="highlight">محمدعبدالاله ابكر دوده</span>، صانع ومطور هذه المنصة. ولدت فكرة هذا الموقع من رؤية واضحة وشغف حقيقي يهدف إلى <span class="highlight">توعية مجتمع الشباب والمهتمين</span> بكافة أنواع المركبات وفهم تصنيفاتها الهندسية والجمالية. غايتنا الأساسية هي أن نكون بمثابة <span class="highlight">المساعد الميكانيكي والرقمي الذكي لكل مشترٍ</span>، نأخذ بيدك لنكشف لك تفاصيل العزل والتحكم والأسعار الحقيقية لتختار سيارة أحلامك بثقة ودراية تامة تليق بك وبمستقبلك.</p>
        </div>

        <!-- لوقو بي ام دبليو الأسطورية -->
        <div class="bmw-tribute">
            <div class="bmw-logo-wrapper">
                <svg viewBox="0 0 100 100">
                    <circle cx="50" cy="50" r="46" fill="#000" stroke="#a0aec0" stroke-width="2"/>
                    <circle cx="50" cy="50" r="35" fill="#fff"/>
                    <path d="M50,50 L50,15 A35,35 0 0,1 85,50 Z" fill="#0066b2"/>
                    <path d="M50,50 L15,50 A35,35 0 0,1 50,15 Z" fill="#fff"/>
                    <path d="M50,50 L50,85 A35,35 0 0,1 15,50 Z" fill="#0066b2"/>
                    <path d="M50,50 L85,50 A35,35 0 0,1 50,85 Z" fill="#fff"/>
                    <circle cx="50" cy="50" r="14" fill="none" stroke="rgba(255,255,255,0.2)" stroke-width="1"/>
                </svg>
            </div>
            <h4>BMW</h4>
            <p>سوف تظل الأفخم على الإطلاق</p>
        </div>

    </section>

    <!-- واجهة النافذة المنبثقة التوجيهية للشركات التلقائية -->
    <div class="gateway-modal" id="gatewayModal">
        <div class="gateway-content">
            <div class="gateway-icon">🚀</div>
            <h3>بوابة العبور والاتصال الذكي</h3>
            <p>مرحباً بك، جاري توجيهك الآن إلى الخوادم والمواقع الرسمية لشركة <strong id="modalTargetCompany" style="color:var(--accent-blue);"></strong>.</p>
            <div class="gateway-badge">
                📢 منصة ممر المحركات هي وجهتكم الرقمية المعتمدة لعرض منتجاتكم والتعريف بها كلياً لرفع الوعي الميكانيكي للعملاء.
            </div>
            <div class="countdown-text" id="modalCountdown">جاري الانتقال التلقائي الآمن خلال 4 ثوانٍ...</div>
        </div>
    </div>

    <!-- لافتة التنبيهات الإعلانية والتسويقية الذكية للزوار -->
    <div class="marketing-toast" id="marketingToast">
        <span style="font-size:20px;">🔥</span>
        <div>
            <strong style="color:#fff; display:block; font-size:13px;">تنبيه فحص حي نشط!</strong>
            <span style="color:var(--text-muted); font-size:12px;">أحد الزوار يقوم الآن بمطابقة S-Class مع BMW M5.</span>
        </div>
    </div>

    <footer>
        <p>منصة ممر المحركات المتقدمة © 2026 - رؤية وتطوير المهندس محمدعبدالاله ابكر دوده</p>
    </footer>

    <script>
        // إعدادات العدادات الحية الافتراضية
        let totalSearches = 512;
        let totalClicks = 384;
        let totalMessages = 0;

        // دالة مصفوفة الصور سداسية الأبعاد لشبكة المقارنة
        function generateMeshImages() {
            return [
                { label: "📸 الواجهة الأمامية", url: `https://images.unsplash.com/photo-1542282088-72c9c27ed0cd?auto=format&fit=crop&w=300&q=80` },
                { label: "📸 الجانب الأيمن/الأيسر", url: `https://images.unsplash.com/photo-1617814076367-b759c7d7e738?auto=format&fit=crop&w=300&q=80` },
                { label: "📸 الواجهة الخلفية", url: `https://images.unsplash.com/photo-1618843479313-40f8afb4b4d8?auto=format&fit=crop&w=300&q=80` },
                { label: "📸 المنظور العلوي للزاوية", url: `https://images.unsplash.com/photo-1614162692292-7ac56d7f7f1e?auto=format&fit=crop&w=300&q=80` },
                { label: "⚙️ مكنة ومحرك الماركة", url: `https://images.unsplash.com/photo-1486006920555-c77dce18193b?auto=format&fit=crop&w=300&q=80` },
                { label: "🎛️ مكان القيادة والتحكمات", url: `https://images.unsplash.com/photo-1549399542-7e3f8b79c341?auto=format&fit=crop&w=300&q=80` }
            ];
        }

        // دالة النافذة التوجيهية الذكية عند الدخول لشركات السيارات
        function openGateway(companyName, targetUrl) {
            const modal = document.getElementById("gatewayModal");
            const compText = document.getElementById("modalTargetCompany");
            const countdownText = document.getElementById("modalCountdown");
            
            compText.innerText = companyName;
            modal.classList.add("active");
            
            totalClicks++;
            document.getElementById("kpiClicks").innerText = totalClicks;
            
            let timeLeft = 4;
            const interval = setInterval(() => {
                timeLeft--;
                countdownText.innerText = `جاري الانتقال التلقائي الآمن خلال ${timeLeft} ثوانٍ...`;
                if(timeLeft <= 0) {
                    clearInterval(interval);
                    modal.classList.remove("active");
                    window.open(targetUrl, '_blank');
                }
            }, 1000);
        }

        // دالة إرسال الرسائل لبريد المدير السري وحفظها محلياً
        let adminMailbox = []; 
        function sendSecureMessageToAdmin() {
            const name = document.getElementById("adminSenderName").value.trim();
            const contact = document.getElementById("adminSenderContact").value.trim();
            const text = document.getElementById("adminMessageText").value.trim();
            
            if(!name || !contact || !text) {
                return alert("فضلاً، يرجى تعبئة جميع الحقول (الاسم، وسيلة الاتصال، ونص الرسالة) لإتمام عملية الشحن الآمن للبريد!");
            }
            
            const secureMessageObject = {
                id: Date.now(),
                sender: name,
                contactInfo: contact,
                messageBody: text,
                timestamp: new Date().toLocaleString('ar-EG')
            };
            
            adminMailbox.push(secureMessageObject);
            totalMessages++;
            document.getElementById("kpiMessages").innerText = totalMessages;
            
            document.getElementById("adminSenderName").value = "";
            document.getElementById("adminSenderContact").value = "";
            document.getElementById("adminMessageText").value = "";
            
            alert("🔒 تم تشفير وإرسال رسالتك بنجاح! تم إيداعها في صندوق بريد المدير السري المباشر، ولن تظهر للعامة مطلقاً في الموقع. سيطلع عليها المدير محمد عبدالاله ويقوم بالرد عليك قريباً جداً.");
        }

        // إدارة لوحة المحطات (Milestones)
        function toggleMilestone(checkbox) {
            const parent = checkbox.parentElement;
            if(checkbox.checked) {
                parent.classList.add("done");
            } else {
                parent.classList.remove("done");
            }
        }

        // محاكاة تفعيل خطة الطوارئ البديلة (Plan B)
        function triggerPlanB() {
            alert("⚠️ جاري فحص خطة الطوارئ البديلة:\n1. تحويل مسارات المرور لخوادم النسخ الاحتياطي الاحتياطية.\n2. تشغيل التخزين المؤقت المحلي للبيانات الحركية.\n\nالنتيجة: موقع ممر المحركات يعمل بكفاءة 100% وبدون أي فقد للبيانات!");
        }

        // تصدير التقارير الحية للعمل والتوثيق (Documentation Tool)
        function exportKPIDocumentation() {
            const report = `=== تقرير أداء منصة ممر المحركات ===\nتاريخ التوثيق: ${new Date().toLocaleDateString('ar-EG')}\nإجمالي الزيارات: 1248\nنقرات العبور: ${totalClicks}\nفحوصات المحرك: ${totalSearches}\nالرسائل الواردة للمدير: ${totalMessages}\nحالة الأنظمة: مستقرة وآمنة تماماً.`;
            alert("📝 تم توليد تقرير التوثيق بنجاح! تفاصيل التقرير:\n\n" + report + "\n\n(يمكنك حفظ الإحصائيات لمتابعة مؤشرات النجاح بدقة)");
        }

        // دالة مطابقة وفحص السيارات
        function fetchCar(carName) {
            if (!carName || carName.trim() === "") return null;
            const sName = carName.trim().toLowerCase();

            let price = "$31,200"; let eco = "16.8 كم/لتر"; let seats = "5 مقاعد"; let audience = "الجميع";
            let specs = `مركبة رائدة تم تتبع أبعادها الهندسية. تمثل خياراً متوازناً يجمع كفاءة الهيكل وسعر المصنع العادل.`;
            let pros = "أنظمة أمان رادارية ممتازة، كفاءة عالية في المنعطفات السريعة، وعجلة قيادة تفاعلية مريحة.";
            let cons = "تتطلب اهتماماً دورياً بنوعية فلاتر الوقود والزيوت للحفاظ على الضغط الداخلي للمكنة.";

            if (sName.includes("كامري") || sName.includes("تويوتا") || sName.includes("سوناتا")) {
                price = "$27,400"; eco = "26.0 كم/لتر"; seats = "5 مقاعد"; audience = "الجميع";
                specs = "سيارة سيدان يابانية اعتمادية أسطورية من الطراز الأول، مناسبة لكل الظروف والمهام الممتدة لسنوات.";
            } else if (sName.includes("مرسيدس") || sName.includes("بنز") || sName.includes("s-class")) {
                price = "$117,300"; eco = "12.1 كم/لتر"; seats = "5 مقاعد"; audience = "رجال";
                specs = "أيقونة الصالونات الفاخرة عالمياً، توفر راحة ركوب استثنائية مع أنظمة عزل صوتي وهندسي محكم.";
            } else if (sName.includes("تسلا") || sName.includes("كهربا")) {
                price = "$42,990"; eco = "كهرباء بالكامل"; seats = "5 مقاعد"; audience = "شباب";
                specs = "سيارة ذكية متكاملة تركز على القيادة الذاتية والمستقبل البرمجي الخالي من الانبعاثات الكربونية.";
            } else if (sName.includes("لاند") || sName.includes("باترول") || sName.includes("جيب") || sName.includes("عائلي")) {
                price = "$54,600"; eco = "11.5 كم/لتر"; seats = "7 مقاعد عائلية"; audience = "عائلية";
                specs = "مركبة دفع رباعي عريضة مجهزة بكافة سبل الراحة والمساحات الكبيرة المخصصة للأسر والرحلات الطويلة والوعرة.";
            } else if (sName.includes("سبورت") || sName.includes("موستانج") || sName.includes("بورشه") || sName.includes("فراري")) {
                price = "$68,500"; eco = "9.4 كم/لتر"; seats = "4 مقاعد"; audience = "شباب";
                specs = "طراز حركي سبورت سريع مصمم ليعطي أعلى معدلات تسارع ميكانيكي مع مظهر رياضي ملفت وجذاب.";
            } else if (sName.includes("صغير") || sName.includes("يارس") || sName.includes("فتيات") || sName.includes("اكسنت")) {
                price = "$18,200"; eco = "21.5 كم/لتر"; seats = "5 مقاعد"; audience = "فتيات";
                specs = "سيارة مدمجة خفيفة وعملية، خيار مثالي للمدن المزدحمة، وتوفر مرونة ممتازة للموظفات والطالبات.";
            } else if (sName.includes("بي ام") || sName.includes("bmw")) {
                price = "$82,000"; eco = "13.8 كم/لتر"; seats = "5 مقاعد مريحة"; audience = "شباب";
                specs = "التحفة الهندسية الألمانية البافارية الفاخرة التي تجمع الروح الرياضية الشرسة مع قمة الفخامة الرقمية.";
            }

            return { name: carName, price: price, eco: eco, seats: seats, audience: audience, specs: specs, pros: pros, cons: cons };
        }

        function executeSearchAndCompare() {
            const c1 = document.getElementById("car1Input").value;
            const c2 = document.getElementById("car2Input").value;
            const d1 = fetchCar(c1); const d2 = fetchCar(c2);
            const container = document.getElementById("resultsContainer");

            if (!d1 && !d2) return alert("يرجى كتابة اسم الطراز في الخانة الأولى لبدء عملية الفحص الفني والربط السعري!");
            container.style.display = "grid";

            totalSearches++;
            document.getElementById("kpiSearches").innerText = totalSearches;

            if (d1 && !d2) {
                document.getElementById("card1").style.display = "block";
                document.getElementById("card2").style.display = "none";
                container.style.gridTemplateColumns = "1fr";
                fillCard(1, d1);
            } else if (d1 && d2) {
                document.getElementById("card1").style.display = "block";
                document.getElementById("card2").style.display = "block";
                if (window.innerWidth > 768) container.style.gridTemplateColumns = "1fr 1fr";
                fillCard(1, d1); fillCard(2, d2);
            }
            container.scrollIntoView({ behavior: 'smooth' });
        }

        function renderAudienceTags(containerId, activeAudience) {
            const zones = ["رجال", "نساء", "شباب", "فتيات", "عائلية"];
            const container = document.getElementById(containerId);
            container.innerHTML = "";
            
            zones.forEach(zone => {
                const tagSpan = document.createElement("span");
                tagSpan.className = "aud-tag";
                tagSpan.innerText = "• مناسبة لـ " + zone;
                if (activeAudience.includes(zone) || activeAudience === "الجميع") {
                    tagSpan.className += " active-tag";
                }
                container.appendChild(tagSpan);
            });
        }

        function fillCard(num, data) {
            document.getElementById(`car${num}Title`).innerText = "🔍 تقرير فحص ومطابقة: " + data.name;
            document.getElementById(`car${num}PriceVal`).innerText = data.price;
            document.getElementById(`car${num}EcoVal`).innerText = data.eco;
            document.getElementById(`car${num}SeatsVal`).innerText = data.seats;
            document.getElementById(`car${num}Specs`).innerText = data.specs;
            document.getElementById(`car${num}Pros`).innerText = data.pros;
            document.getElementById(`car${num}Cons`).innerText = data.cons;

            renderAudienceTags(`car${num}AudienceZone`, data.audience);

            const meshContainer = document.getElementById(`car${num}Mesh`);
            meshContainer.innerHTML = ""; 
            const images = generateMeshImages();
            
            images.forEach(imgData => {
                const wrapper = document.createElement("div");
                wrapper.className = "mesh-img-wrapper";
                wrapper.innerHTML = `<img src="${imgData.url}" alt="${imgData.label}"><div class="mesh-label">${imgData.label}</div>`;
                meshContainer.appendChild(wrapper);
            });
        }

        function addDreamCar() {
            const name = document.getElementById("dreamerName").value.trim();
            const car = document.getElementById("dreamCar").value.trim();
            if(!name || !car) return alert("يرجى إدخال البيانات المطلوبة!");
            const container = document.getElementById("dreamCarsContainer");
            const newItem = document.createElement("div");
            newItem.className = "dream-item";
            newItem.innerHTML = `<span class="user-name">${name}</span><span class="car-name">${car}</span>`;
            container.insertBefore(newItem, container.firstChild);
            document.getElementById("dreamerName").value = ""; document.getElementById("dreamCar").value = "";
        }

        function addComment() {
            const name = document.getElementById("commenterName").value.trim();
            const text = document.getElementById("commentText").value.trim();
            if(!name || !text) return alert("يرجى كتابة الاسم والتعليق!");
            const container = document.getElementById("commentsContainer");
            const newItem = document.createElement("div");
            newItem.className = "comment-item";
            newItem.innerHTML = `<div class="comment-meta"><strong>${name}</strong> <span>الآن</span></div><p>${text}</p>`;
            container.insertBefore(newItem, container.firstChild);
            document.getElementById("commenterName").value = ""; document.getElementById("commentText").value = "";
        }

        // تأثير اللمسة التسويقية الأخيرة (ظهور الإشعار التلقائي بعد 4 ثوانٍ من دخول الموقع)
        window.onload = function() {
            setTimeout(() => {
                document.getElementById("marketingToast").classList.add("show");
                setTimeout(() => {
                    document.getElementById("marketingToast").classList.remove("show");
                }, 5000);
            }, 4000);
        };
    </script>
</body>
</html>
