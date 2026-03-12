<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amazon倉庫 × データベース知識 活用ガイド</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Noto Sans JP', sans-serif; background-color: #f8fafc; color: #334155; }
        .card-hover { transition: transform 0.2s ease, box-shadow 0.2s ease; }
        .card-hover:hover { transform: translateY(-4px); box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1); }
    </style>
</head>
<body class="antialiased">

    <!-- Header -->
    <header class="bg-gradient-to-r from-slate-800 to-slate-900 text-white py-12 px-4 border-b-4 border-orange-500 shadow-lg">
        <div class="container mx-auto max-w-5xl text-center">
            <div class="inline-block bg-orange-500 text-white px-3 py-1 rounded-full text-xs font-bold mb-4 tracking-wider">
                LOGISTICS × ENGINEERING
            </div>
            <h1 class="text-3xl md:text-4xl font-black mb-4 tracking-tight">
                データベース知識が<br class="md:hidden"><span class="text-orange-400">Amazon倉庫</span>でどう役立つか？
            </h1>
            <p class="text-slate-300 font-medium max-w-2xl mx-auto leading-relaxed">
                現場の物理的な動き（モノの流れ）と、システムの動き（データの流れ）を<br class="hidden md:block">
                直感的に結びつけて理解するための5つのコアスキル。
            </p>
        </div>
    </header>

    <main class="container mx-auto max-w-5xl px-4 py-12">
        
        <!-- Quick Reference Grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-16">
            
            <!-- Skill 1 -->
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200 card-hover">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-3xl">📦</span>
                    <span class="text-xs font-bold bg-blue-100 text-blue-800 px-2 py-1 rounded">ACID特性</span>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2">1. トランザクション / 排他制御</h3>
                <p class="text-sm font-bold text-orange-600 mb-3 border-b pb-2">🎯 在庫の「ズレ」を防ぐ</p>
                <p class="text-xs text-slate-600 leading-relaxed">
                    システム上の在庫と物理在庫の致命的な不一致を防止。「同時にピッキングされた時」のデータロックの仕組みを理解する。
                </p>
            </div>

            <!-- Skill 2 -->
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200 card-hover">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-3xl">🧩</span>
                    <span class="text-xs font-bold bg-purple-100 text-purple-800 px-2 py-1 rounded">NoSQL / KVS</span>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2">2. キーバリューストア</h3>
                <p class="text-sm font-bold text-orange-600 mb-3 border-b pb-2">🎯 「カオス収納」の理解</p>
                <p class="text-xs text-slate-600 leading-relaxed">
                    商品をバラバラの棚に入れても超高速で探し出せる理由。バーコード同士を1対1でシンプルに紐付けるシステム的合理性。
                </p>
            </div>

            <!-- Skill 3 -->
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200 card-hover">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-3xl">⚡</span>
                    <span class="text-xs font-bold bg-green-100 text-green-800 px-2 py-1 rounded">Index</span>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2">3. インデックスと検索最適化</h3>
                <p class="text-sm font-bold text-orange-600 mb-3 border-b pb-2">🎯 スキャナーの応答速度改善</p>
                <p class="text-xs text-slate-600 leading-relaxed">
                    数千万件のデータから0.1秒で商品を見つける仕組み。バーコード読み取り時のタイムラグ（塵積のロス）を解消する。
                </p>
            </div>

            <!-- Skill 4 -->
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200 card-hover">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-3xl">📊</span>
                    <span class="text-xs font-bold bg-rose-100 text-rose-800 px-2 py-1 rounded">SQL</span>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2">4. データ抽出・集計</h3>
                <p class="text-sm font-bold text-orange-600 mb-3 border-b pb-2">🎯 現場のボトルネック発見</p>
                <p class="text-xs text-slate-600 leading-relaxed">
                    特定の通路の渋滞やエラー頻発エリアをデータから特定。人員配置の最適化やレイアウト変更の根拠を作る。
                </p>
            </div>

            <!-- Skill 5 -->
            <div class="bg-white rounded-2xl p-6 shadow-sm border border-slate-200 card-hover">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-3xl">🏗️</span>
                    <span class="text-xs font-bold bg-amber-100 text-amber-800 px-2 py-1 rounded">Table Design</span>
                </div>
                <h3 class="text-lg font-bold text-slate-800 mb-2">5. データモデル設計</h3>
                <p class="text-sm font-bold text-orange-600 mb-3 border-b pb-2">🎯 新しい業務フローの提案</p>
                <p class="text-xs text-slate-600 leading-relaxed">
                    商品・在庫・棚のテーブルの紐付き（リレーション）をイメージし、賞味期限管理などの新しいルールをシステム要件に翻訳する。
                </p>
            </div>
            
            <!-- Summary Card -->
            <div class="bg-slate-800 rounded-2xl p-6 shadow-sm border border-slate-700 text-white flex flex-col justify-center">
                <h3 class="text-lg font-bold text-orange-400 mb-2">💡 究極の視点</h3>
                <p class="text-sm leading-relaxed">
                    「目の前にあるダンボールは、データベース上の1行のレコード（データ）である」と変換して捉える力が、高度に自動化された物流拠点で最大の武器になります。
                </p>
            </div>

        </div>

        <!-- Example Section (SQL) -->
        <section class="bg-white rounded-2xl shadow-sm border border-slate-200 overflow-hidden">
            <div class="bg-slate-50 border-b border-slate-200 px-6 py-4">
                <h2 class="text-lg font-bold text-slate-800 flex items-center gap-2">
                    <span>💻</span> 実践例：SQLで現場の渋滞を特定する
                </h2>
            </div>
            <div class="p-6 md:flex gap-8 items-center">
                <div class="md:w-1/2 mb-6 md:mb-0">
                    <p class="text-sm text-slate-600 leading-relaxed mb-4">
                        マネージャーや改善担当者になった際、SQLは最強の武器になります。<br>
                        例えば右のコードのように書くことで、<strong>「どのエリアで、何回遅延（5分以上のピッキング待ち）が発生しているか」</strong>を一瞬でランキング化できます。
                    </p>
                    <p class="text-sm text-slate-600 leading-relaxed">
                        これをもとに「エリアAの棚の配置を変えよう」「人員を補充しよう」といったデータドリブンな改善が可能になります。
                    </p>
                </div>
                <div class="md:w-1/2 bg-slate-900 rounded-xl p-5 shadow-inner">
                    <pre class="text-xs md:text-sm text-green-400 font-mono overflow-x-auto"><code><span class="text-purple-400">SELECT</span> 
    エリア, 
    <span class="text-blue-400">COUNT</span>(*) <span class="text-purple-400">AS</span> 遅延発生回数
<span class="text-purple-400">FROM</span> 
    ピッキング履歴 
<span class="text-purple-400">WHERE</span> 
    遅延時間 > <span class="text-orange-300">5</span>分 
<span class="text-purple-400">GROUP BY</span> 
    エリア
<span class="text-purple-400">ORDER BY</span>
    遅延発生回数 <span class="text-purple-400">DESC</span>;</code></pre>
                </div>
            </div>
        </section>

    </main>

</body>
</html>
