# HTML構造ガイド

## 基本テンプレート

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>【機能名】 - Google新機能図解</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --google-blue: #4285F4;
      --google-red: #EA4335;
      --google-yellow: #FBBC05;
      --google-green: #34A853;
    }
    body { font-family: 'Noto Sans JP', 'Inter', sans-serif; }
  </style>
</head>
<body class="bg-gray-50">

  <!-- ヘッダー -->
  <!-- メインコンテンツ -->
  <!-- Lucide初期化 -->
  <script>lucide.createIcons();</script>
</body>
</html>
```

---

## ヘッダー

機能名・製品バッジ・発表日を表示。

```html
<header style="background: linear-gradient(135deg, #4285F4 0%, #34A853 100%);" class="text-white py-10">
  <div class="max-w-3xl mx-auto px-4">
    <!-- 製品バッジ -->
    <div class="flex flex-wrap gap-2 mb-4">
      <span class="bg-white bg-opacity-20 text-white text-sm font-semibold px-3 py-1 rounded-full">
        Google Workspace
      </span>
      <span class="bg-white bg-opacity-20 text-white text-sm px-3 py-1 rounded-full">
        2025年3月発表
      </span>
    </div>
    <!-- タイトル -->
    <h1 class="text-3xl md:text-4xl font-bold leading-tight">
      Gemini in Gmail<br>
      <span class="text-2xl md:text-3xl font-normal opacity-90">メール作成AIアシスタント</span>
    </h1>
  </div>
</header>
```

---

## 一言サマリーカード

変更の核心を1文 + ビフォーアフターで見せる。

```html
<div class="max-w-3xl mx-auto px-4 -mt-6">
  <div class="bg-white rounded-2xl shadow-lg p-6 mb-6">

    <!-- 一言サマリー -->
    <div class="flex items-start gap-3 mb-6">
      <div class="w-10 h-10 rounded-xl flex items-center justify-center flex-shrink-0"
           style="background-color: #E8F0FE;">
        <i data-lucide="zap" class="w-5 h-5" style="color: #4285F4;"></i>
      </div>
      <div>
        <div class="text-xs font-semibold uppercase tracking-wide text-gray-400 mb-1">これで何ができるようになった？</div>
        <p class="text-lg font-bold text-gray-800">
          GmailでAIがメールの下書きを自動生成できるようになった。
        </p>
      </div>
    </div>

    <!-- ビフォーアフター -->
    <div class="grid md:grid-cols-2 gap-4">
      <div class="bg-red-50 border border-red-200 rounded-xl p-4">
        <div class="flex items-center gap-2 mb-2">
          <i data-lucide="x-circle" class="w-4 h-4 text-red-500"></i>
          <span class="text-sm font-bold text-red-700">今まで</span>
        </div>
        <p class="text-gray-700 text-sm">自分でゼロからメールを書く必要があった。件名・宛名・本文すべて手入力。</p>
      </div>
      <div class="bg-green-50 border border-green-200 rounded-xl p-4">
        <div class="flex items-center gap-2 mb-2">
          <i data-lucide="check-circle" class="w-4 h-4 text-green-500"></i>
          <span class="text-sm font-bold text-green-700">これから</span>
        </div>
        <p class="text-gray-700 text-sm">「〇〇についてお礼のメールを書いて」と指示するだけで下書きが完成。</p>
      </div>
    </div>

    <!-- 対象・条件 -->
    <div class="mt-4 flex flex-wrap gap-2">
      <span class="inline-flex items-center gap-1 text-xs bg-blue-100 text-blue-700 px-3 py-1 rounded-full">
        <i data-lucide="users" class="w-3 h-3"></i>
        Google Workspace Business以上
      </span>
      <span class="inline-flex items-center gap-1 text-xs bg-gray-100 text-gray-600 px-3 py-1 rounded-full">
        <i data-lucide="globe" class="w-3 h-3"></i>
        日本語対応済み
      </span>
    </div>
  </div>
</div>
```

---

## 今すぐ試せる手順

番号付きステップ形式（必須セクション）。

```html
<div class="max-w-3xl mx-auto px-4 mb-6">
  <div class="bg-white rounded-2xl shadow-sm p-6">

    <!-- セクションヘッダー -->
    <div class="flex items-center gap-3 mb-6">
      <div class="w-10 h-10 rounded-xl flex items-center justify-center"
           style="background-color: #E6F4EA;">
        <i data-lucide="play-circle" class="w-5 h-5" style="color: #34A853;"></i>
      </div>
      <div>
        <h2 class="text-xl font-bold text-gray-800">今すぐ試せる手順</h2>
        <p class="text-sm text-gray-500">この操作をすれば使える</p>
      </div>
    </div>

    <!-- ステップリスト -->
    <ol class="space-y-4">
      <li class="flex gap-4">
        <div class="w-8 h-8 rounded-full flex items-center justify-center text-white font-bold text-sm flex-shrink-0"
             style="background-color: #4285F4;">1</div>
        <div class="flex-1 pt-1">
          <p class="font-semibold text-gray-800">Gmailを開く</p>
          <p class="text-sm text-gray-600 mt-1">gmail.com にアクセスし、Googleアカウントでログインする。</p>
        </div>
      </li>
      <li class="flex gap-4">
        <div class="w-8 h-8 rounded-full flex items-center justify-center text-white font-bold text-sm flex-shrink-0"
             style="background-color: #34A853;">2</div>
        <div class="flex-1 pt-1">
          <p class="font-semibold text-gray-800">「作成」ボタンをクリック</p>
          <p class="text-sm text-gray-600 mt-1">左上の「作成」ボタンを押して新規メール作成画面を開く。</p>
        </div>
      </li>
      <li class="flex gap-4">
        <div class="w-8 h-8 rounded-full flex items-center justify-center text-white font-bold text-sm flex-shrink-0"
             style="background-color: #FBBC05;">3</div>
        <div class="flex-1 pt-1">
          <p class="font-semibold text-gray-800">Geminiアイコンをクリック</p>
          <p class="text-sm text-gray-600 mt-1">メール作成エリアの右下にある星形アイコン（Gemini）をクリックする。</p>
        </div>
      </li>
      <li class="flex gap-4">
        <div class="w-8 h-8 rounded-full flex items-center justify-center text-white font-bold text-sm flex-shrink-0"
             style="background-color: #EA4335;">4</div>
        <div class="flex-1 pt-1">
          <p class="font-semibold text-gray-800">やりたいことを日本語で入力</p>
          <p class="text-sm text-gray-600 mt-1">例：「先日の打ち合わせのお礼メールを丁寧な敬語で書いて」と入力して送信。</p>
        </div>
      </li>
    </ol>
  </div>
</div>
```

---

## フリーランス活用ポイント

AI学習中・フリーランス志望の観点で使いどころを示す。

```html
<div class="max-w-3xl mx-auto px-4 mb-6">
  <div class="bg-white rounded-2xl shadow-sm p-6">

    <div class="flex items-center gap-3 mb-6">
      <div class="w-10 h-10 rounded-xl flex items-center justify-center"
           style="background-color: #FEF3E2;">
        <i data-lucide="briefcase" class="w-5 h-5" style="color: #FBBC05;"></i>
      </div>
      <div>
        <h2 class="text-xl font-bold text-gray-800">フリーランス活用ポイント</h2>
        <p class="text-sm text-gray-500">AIフリーランスとして使えるシーン</p>
      </div>
    </div>

    <div class="grid gap-4">
      <!-- 活用例カード -->
      <div class="border border-gray-200 rounded-xl p-4 hover:border-blue-300 transition-colors">
        <div class="flex items-start gap-3">
          <i data-lucide="mail" class="w-5 h-5 text-blue-500 flex-shrink-0 mt-0.5"></i>
          <div>
            <p class="font-semibold text-gray-800">クライアントへの提案メール</p>
            <p class="text-sm text-gray-600 mt-1">
              案件ごとのお礼・見積もり送付・進捗報告を素早く作成。
              メール作業の時間を半分以下にできる。
            </p>
          </div>
        </div>
      </div>

      <div class="border border-gray-200 rounded-xl p-4 hover:border-green-300 transition-colors">
        <div class="flex items-start gap-3">
          <i data-lucide="repeat" class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"></i>
          <div>
            <p class="font-semibold text-gray-800">定型メールのテンプレ化</p>
            <p class="text-sm text-gray-600 mt-1">
              初回連絡・納品通知・請求書送付など繰り返すメールをAIに覚えさせ、毎回1分以内で送信。
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```

---

## 知っておくと便利な補足

制限・注意点・関連機能を載せる。

```html
<div class="max-w-3xl mx-auto px-4 mb-6">
  <div class="bg-white rounded-2xl shadow-sm p-6">

    <div class="flex items-center gap-3 mb-4">
      <i data-lucide="info" class="w-5 h-5 text-gray-500"></i>
      <h2 class="text-lg font-bold text-gray-700">知っておくと便利な補足</h2>
    </div>

    <ul class="space-y-3">
      <li class="flex items-start gap-2 text-sm text-gray-700">
        <i data-lucide="alert-circle" class="w-4 h-4 text-yellow-500 flex-shrink-0 mt-0.5"></i>
        <span><strong>利用条件:</strong> Google Workspace Business Starter以上のプランが必要。個人のGmailアカウントでは使えない。</span>
      </li>
      <li class="flex items-start gap-2 text-sm text-gray-700">
        <i data-lucide="link" class="w-4 h-4 text-blue-500 flex-shrink-0 mt-0.5"></i>
        <span><strong>関連機能:</strong> Google Meetの議事録自動生成、Google Docsの文章改善にも同様のGemini機能がある。</span>
      </li>
    </ul>
  </div>
</div>
```

---

## 出典リンク

```html
<div class="max-w-3xl mx-auto px-4 mb-10">
  <div class="border border-gray-200 rounded-xl p-4">
    <div class="flex items-center gap-2 mb-3">
      <i data-lucide="external-link" class="w-4 h-4 text-gray-400"></i>
      <span class="text-sm font-semibold text-gray-500">出典・参考リンク</span>
    </div>
    <ul class="space-y-2">
      <li>
        <a href="https://workspace.google.com/blog/" 
           class="text-sm text-blue-600 hover:underline flex items-center gap-1" 
           target="_blank" rel="noopener">
          <i data-lucide="arrow-up-right" class="w-3 h-3"></i>
          Google Workspace 公式ブログ
        </a>
      </li>
    </ul>
  </div>
</div>
```

---

## Lucide Icon よく使うアイコン

| 用途 | アイコン名 |
|------|----------|
| 変化・アップデート | `zap`, `sparkles`, `refresh-cw` |
| 手順・操作 | `play-circle`, `mouse-pointer-click`, `hand` |
| 確認・OK | `check-circle`, `shield-check` |
| 注意 | `alert-circle`, `triangle-alert` |
| 仕事・フリーランス | `briefcase`, `dollar-sign`, `clock` |
| Google製品系 | `mail`, `calendar`, `file-text`, `search`, `video` |
| 情報・リンク | `info`, `external-link`, `link`, `arrow-up-right` |

### 基本構文

```html
<i data-lucide="icon-name" class="w-5 h-5 text-blue-500"></i>
```

---

## Googleカラーの使い方

| 色 | HEX | 用途 |
|----|-----|------|
| Google Blue | `#4285F4` | ヘッダー、主要アクション、手順番号 |
| Google Green | `#34A853` | 成功・「今すぐ試せる」セクション |
| Google Yellow | `#FBBC05` | フリーランス活用・注意点 |
| Google Red | `#EA4335` | 変更前・注意・制限 |

Tailwindのインラインスタイルで使う（`style="color: #4285F4;"` の形式）。
Tailwindの標準カラー（`text-blue-500`等）は近似値として利用可。
