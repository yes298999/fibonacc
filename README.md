<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>費波南希數列計算器</title>
 <!-- 					【版權宣言】
		程式編寫員: 富途 “超級幸運兒16813298” 編寫及完全免費分享. 
		【發哥免費指標王】港美股票交流討論群組，分享更多免費指標： 
		https://snsim.futunn.com/share/group/688tS?lang=zh-hk
 -->
    
    <!-- 配置Tailwind自定義顏色和字體 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#3B82F6',
                        secondary: '#10B981',
                        accent: '#8B5CF6',
                        neutral: '#1F2937',
                    },
                    fontFamily: {
                        sans: ['Noto Sans TC', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .input-focus {
                @apply focus:ring-2 focus:ring-primary/50 focus:border-primary focus:outline-none;
            }
            .card-shadow {
                @apply shadow-lg hover:shadow-xl transition-shadow duration-300;
            }
            .btn-effect {
                @apply transform hover:-translate-y-1 transition-transform duration-200;
            }
        }
    </style>
    
    <!-- Tailwind CSS v3 核心代碼 -->
    <style>
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
        }
    </style>
    <style>
        *, ::before, ::after {
            box-sizing: border-box;
            border-width: 0;
            border-style: solid;
            border-color: #e5e7eb;
        }
        ::before, ::after {
            --tw-content: '';
        }
        html {
            line-height: 1.5;
            -webkit-text-size-adjust: 100%;
            -moz-tab-size: 4;
            tab-size: 4;
            font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
            font-feature-settings: normal;
            font-variation-settings: normal;
        }
        body {
            margin: 0;
            line-height: inherit;
        }
        hr {
            height: 0;
            color: inherit;
            border-top-width: 1px;
        }
        abbr:where([title]) {
            -webkit-text-decoration: underline dotted;
            text-decoration: underline dotted;
        }
        h1, h2, h3, h4, h5, h6 {
            font-size: inherit;
            font-weight: inherit;
        }
        a {
            color: inherit;
            text-decoration: inherit;
        }
        b, strong {
            font-weight: bolder;
        }
        code, kbd, samp, pre {
            font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
            font-size: 1em;
        }
        small {
            font-size: 80%;
        }
        sub, sup {
            font-size: 75%;
            line-height: 0;
            position: relative;
            vertical-align: baseline;
        }
        sub {
            bottom: -.25em;
        }
        sup {
            top: -.5em;
        }
        table {
            text-indent: 0;
            border-color: inherit;
            border-collapse: collapse;
        }
        button, input, optgroup, select, textarea {
            font-family: inherit;
            font-size: 100%;
            font-weight: inherit;
            line-height: inherit;
            color: inherit;
            margin: 0;
            padding: 0;
        }
        button, select {
            text-transform: none;
        }
        [type=button], [type=reset], [type=submit], button {
            -webkit-appearance: button;
            background-color: transparent;
            background-image: none;
        }
        :-moz-focusring {
            outline: auto;
        }
        :-moz-ui-invalid {
            box-shadow: none;
        }
        progress {
            vertical-align: baseline;
        }
        [type=search] {
            -webkit-appearance: textfield;
            outline-offset: -2px;
        }
        ::-webkit-search-decoration {
            -webkit-appearance: none;
        }
        ::-webkit-file-upload-button {
            -webkit-appearance: button;
            font: inherit;
        }
        summary {
            display: list-item;
        }
        blockquote, dl, dd, h1, h2, h3, h4, h5, h6, hr, figure, p, pre {
            margin: 0;
        }
        fieldset {
            margin: 0;
            padding: 0;
        }
        legend {
            padding: 0;
        }
        menu, ol, ul {
            list-style: none;
            margin: 0;
            padding: 0;
        }
        dialog {
            padding: 0;
        }
        textarea {
            resize: vertical;
        }
        input::placeholder, textarea::placeholder {
            opacity: 1;
            color: #9ca3af;
        }
        [role=button], button {
            cursor: pointer;
        }
        :disabled {
            cursor: default;
        }
        audio, canvas, embed, iframe, img, object, svg, video {
            display: block;
            vertical-align: middle;
        }
        img, video {
            max-width: 100%;
            height: auto;
        }
        [hidden] {
            display: none;
        }
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }
        .container {
            width: 100%;
			background-color:#e8f5e9
        }
        @media (min-width: 640px) {
            .container {
                max-width: 640px;				
            }
        }
        @media (min-width: 768px) {
            .container {
                max-width: 768px;				
            }
        }
        @media (min-width: 1024px) {
            .container {
                max-width: 1024px;
            }
        }
        @media (min-width: 1280px) {
            .container {
                max-width: 1280px;
            }
        }
        @media (min-width: 1536px) {
            .container {
                max-width: 1536px;
            }
        }
        .mx-auto {
            margin-left: auto;
            margin-right: auto;
        }
        .mb-2 {
            margin-bottom: 0.5rem;
        }
        .mb-4 {
            margin-bottom: 1rem;
        }
        .mb-6 {
            margin-bottom: 1.5rem;
        }
        .mb-8 {
            margin-bottom: 2rem;
        }
        .mt-1 {
            margin-top: 0.25rem;
        }
        .mt-12 {
            margin-top: 3rem;
        }
        .mt-2 {
            margin-top: 0.5rem;
        }
        .inline-flex {
            display: inline-flex;
        }
        .flex {
            display: flex;
        }
        .table {
            display: table;
        }
        .hidden {
            display: none;
        }
        .h-3 {
            height: 0.75rem;
        }
        .h-5 {
            height: 1.25rem;
        }
        .min-h-screen {
            min-height: 100vh;
        }
        .w-3 {
            width: 0.75rem;
        }
        .w-5 {
            width: 1.25rem;
        }
        .w-20 {
            width: 5rem;
        }
        .w-full {
            width: 100%;
        }
        .min-w-0 {
            min-width: 0px;
        }
        .max-w-3xl {
            max-width: 48rem;
        }
        .flex-1 {
            flex: 1 1 0%;
        }
        .flex-wrap {
            flex-wrap: wrap;
        }
        .items-center {
            align-items: center;
        }
        .items-start {
            align-items: flex-start;
        }
        .justify-center {
            justify-content: center;
        }
        .justify-between {
            justify-content: space-between;
        }
        .gap-2 {
            gap: 0.5rem;
        }
        .gap-3 {
            gap: 0.75rem;
        }
        .gap-4 {
            gap: 1rem;
        }
        .gap-6 {
            gap: 1.5rem;
        }
        .self-center {
            align-self: center;
        }
        .overflow-hidden {
            overflow: hidden;
        }
        .rounded-full {
            border-radius: 9999px;
        }
        .rounded-lg {
            border-radius: 0.5rem;
        }
        .rounded-xl {
            border-radius: 0.75rem;
        }
        .border {
            border-width: 1px;
        }
        .border-gray-200 {
            border-color: #e5e7eb;
        }
        .border-gray-300 {
            border-color: #d1d5db;
        }
        .border-red-500 {
            border-color: #ef4444;
        }
        .bg-gray-50 {
            background-color: #f9fafb;
        }
        .bg-green-700 {
            background-color: #166534;
        }
        .bg-primary {
            background-color: #3B82F6;
        }
        .bg-red-50 {
            background-color: #fef2f2;
        }
        .bg-secondary {
            background-color: #10B981;
        }
        .bg-white {
            background-color: #ffffff;
        }
        .p-2 {
            padding: 0.5rem;
        }
        .p-6 {
            padding: 1.5rem;
        }
        .p-8 {
            padding: 2rem;
        }
        .px-4 {
            padding-left: 1rem;
            padding-right: 1rem;
        }
        .py-2 {
            padding-top: 0.5rem;
            padding-bottom: 0.5rem;
        }
        .py-3 {
            padding-top: 0.75rem;
            padding-bottom: 0.75rem;
        }
        .py-8 {
            padding-top: 2rem;
            padding-bottom: 2rem;
        }
        .pl-3 {
            padding-left: 0.75rem;
        }
        .pl-8 {
            padding-left: 2rem;
        }
        .pb-2 {
            padding-bottom: 0.5rem;
        }
        .pt-2 {
            padding-top: 0.5rem;
        }
        .text-center {
            text-align: center;
        }
        .text-sm {
            font-size: 0.875rem;
            line-height: 1.25rem;
        }
        .text-xs {
            font-size: 0.75rem;
            line-height: 1rem;
        }
        .text-xl {
            font-size: 1.25rem;
            line-height: 1.75rem;
        }
        .font-bold {
            font-weight: 700;
        }
        .font-medium {
            font-weight: 500;
        }
        .font-semibold {
            font-weight: 600;
        }
        .uppercase {
            text-transform: uppercase;
        }
        .leading-relaxed {
            line-height: 1.625;
        }
        .leading-tight {
            line-height: 1.25;
        }
        .text-gray-500 {
            color: #6b7280;
        }
        .text-gray-600 {
            color: #4b5563;
        }
        .text-gray-700 {
            color: #374151;
        }
        .text-green-600 {
            color: #16a34a;
        }
        .text-neutral {
            color: #1F2937;
        }
        .text-primary {
            color: #3B82F6;
        }
        .text-red-500 {
            color: #ef4444;
        }
        .text-white {
            color: #ffffff;
        }
        .underline {
            text-decoration-line: underline;
        }
        .whitespace-pre-line {
            white-space: pre-line;
        }
        .hover\:bg-green-700:hover {
            background-color: #166534;
        }
        .hover\:bg-primary\/90:hover {
            background-color: rgba(59, 130, 246, 0.9);
        }
        .hover\:bg-secondary\/90:hover {
            background-color: rgba(16, 185, 129, 0.9);
        }
        .hover\:shadow-xl:hover {
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
        }
        .focus\:border-primary:focus {
            border-color: #3B82F6;
        }
        .focus\:outline-none:focus {
            outline: 2px solid transparent;
            outline-offset: 2px;
        }
        .focus\:ring-2:focus {
            ring-width: 2px;
        }
        .focus\:ring-primary\/50:focus {
            ring-color: rgba(59, 130, 246, 0.5);
        }
        .peer:checked ~ .peer-checked\:border-primary {
            border-color: #3B82F6;
        }
        .peer:checked ~ .peer-checked\:bg-primary {
            background-color: #3B82F6;
        }
        .peer:checked ~ .peer-checked\:scale-100 {
            transform: scale(1);
        }
        .scale-0 {
            transform: scale(0);
        }
        .shadow-lg {
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .transition-all {
            transition-property: all;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        .transition-colors {
            transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        .transition-shadow {
            transition-property: box-shadow;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        .transition-transform {
            transition-property: transform;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        .duration-200 {
            transition-duration: 200ms;
        }
        .duration-300 {
            transition-duration: 300ms;
        }
        .transform {
            transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
        }
        .hover\:-translate-y-1:hover {
            --tw-translate-y: -0.25rem;
        }
        .cursor-pointer {
            cursor: pointer;
        }
        .overflow-hidden {
            overflow: hidden;
        }
        .relative {
            position: relative;
        }
        .absolute {
            position: absolute;
        }
        .inset-y-0 {
            top: 0px;
            bottom: 0px;
        }
        .left-0 {
            left: 0px;
        }
        .top-0 {
            top: 0px;
        }
        .z-10 {
            z-index: 10;
        }
        .border-b {
            border-bottom-width: 1px;
        }
        .aspect-square {
            aspect-ratio: 1 / 1;
        }
        .object-cover {
            object-fit: cover;
        }
        .clip-circle {
            clip-path: circle(50% at 50% 50%);
        }
        @media (min-width: 640px) {
            .sm\:flex-row {
                flex-direction: row;
            }
            .sm\:items-center {
                align-items: center;
            }
        }
        @media (min-width: 768px) {
            .md\:p-8 {
                padding: 2rem;
            }
        }
        @media (min-width: 1024px) {
            .lg\:flex-row {
                flex-direction: row;
            }
        }
        @supports (clip-path: circle(50%)) {
            .clip-circle {
                clip-path: circle(50%);
            }
        }
        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }
        @keyframes ping {
            75%, 100% {
                transform: scale(2);
                opacity: 0;
            }
        }
        @keyframes pulse {
            50% {
                opacity: 0.5;
            }
        }
        @keyframes bounce {
            0%, 100% {
                transform: translateY(-25%);
                animation-timing-function: cubic-bezier(0.8, 0, 1, 1);
            }
            50% {
                transform: translateY(0);
                animation-timing-function: cubic-bezier(0, 0, 0.2, 1);
            }
        }
        .content-visibility-auto {
            content-visibility: auto;
        }
        .input-focus:focus {
            --tw-ring-opacity: 1;
            --tw-ring-color: rgba(59, 130, 246, 0.5);
            --tw-ring-offset-width: 0px;
            --tw-ring-offset-color: #fff;
            --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
            --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
            box-shadow: var(--tw-ring-offset-shadow), var(--tw-ring-shadow), var(--tw-shadow, 0 0 #0000);
            --tw-border-opacity: 1;
            border-color: rgb(59 130 246 / var(--tw-border-opacity));
            outline: 2px solid transparent;
            outline-offset: 2px;
        }
        .card-shadow {
            --tw-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
        }
        .card-shadow:hover {
            --tw-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
            box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
            transition-property: box-shadow;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 300ms;
        }
        .btn-effect {
            transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
        }
        .btn-effect:hover {
            --tw-translate-y: -0.25rem;
            transition-property: transform;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 200ms;
        }
    </style>
    
    <!-- 自定義圖標替代Font Awesome -->
    <style>
        .icon {
            display: inline-block;
            width: 1em;
            height: 1em;
            stroke-width: 0;
            stroke: currentColor;
            fill: currentColor;
            vertical-align: middle;
        }
        
        .icon-calculator {
            position: relative;
            width: 1em;
            height: 1em;
        }
        
        .icon-calculator::before {
            content: "✖";
            position: absolute;
            top: -0.1em;
            left: 0.3em;
            font-size: 0.7em;
        }
        
        .icon-calculator::after {
            content: "=";
            position: absolute;
            bottom: 0.1em;
            left: 0.2em;
            font-size: 0.6em;
        }
        
        .icon-copy {
            position: relative;
            width: 1em;
            height: 1em;
        }
        
        .icon-copy::before {
            content: "📋";
            font-size: 1em;
        }
        
        .icon-check-circle {
            position: relative;
            width: 1em;
            height: 1em;
        }
        
        .icon-check-circle::before {
            content: "✓";
            position: absolute;
            top: 0;
            left: 0;
            font-size: 1em;
        }
    </style>
</head>
<body class="bg-gray-50 min-h-screen font-sans text-neutral">
    <div class="container mx-auto px-4 py-8 max-w-3xl">
        <!-- 頁面標題 -->
        <header class="text-center mb-8">
			<h1 style="font-size: 2.0rem !important;" class="font-bold text-neutral mb-2 text-primary">費波南希數列自動計算器</h1>
            <p class="text-gray-600"><a href='https://snsim.futunn.com/share/group/688tS?lang=zh-hk' target='_blank'>由 富途 【發哥免費指標王】 編寫免費分享</a></p>
        </header>
        
        <!-- 計算卡片 -->
        <div class="bg-white rounded-xl p-6 md:p-8 card-shadow mb-8">
            <!-- 輸入區域 -->
            <div class="space-y-6">
                <!-- 最高點和最低點輸入（同一行） -->
                <div class="flex flex-col sm:flex-row gap-4 items-start sm:items-center">
                    <!-- 最高點輸入 -->
                    <div class="flex-1 min-w-0">
                        <label for="high" class="block text-sm font-medium text-gray-700 mb-1">
                            最高點 <span class="text-red-500">*</span>
                        </label>
                        <div class="relative">
                            <span id="highCurrencySymbol" class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-500">$</span>
                            <input 
                                type="text" 
                                id="high" 
                                class="pl-8 w-full rounded-lg border border-gray-300 py-2 px-4 input-focus text-sm"
                                placeholder="請輸入最高點數值"
                            >
                        </div>
                        <p id="highError" class="text-red-500 text-xs hidden">請輸入有效的數值</p>
                    </div>
                    
                    <!-- 最低點輸入 -->
                    <div class="flex-1 min-w-0">
                        <label for="low" class="block text-sm font-medium text-gray-700 mb-1">
                            最低點 <span class="text-red-500">*</span>
                        </label>
                        <div class="relative">
                            <span id="lowCurrencySymbol" class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-500">$</span>
                            <input 
                                type="text" 
                                id="low" 
                                class="pl-8 w-full rounded-lg border border-gray-300 py-2 px-4 input-focus text-sm"
                                placeholder="請輸入最低點數值"
                            >
                        </div>
                        <p id="lowError" class="text-red-500 text-xs hidden">請輸入有效的數值</p>
                    </div>
                </div>
                
                <!-- 計算類型和計算對象放在同一行 -->
                <div class="flex flex-col lg:flex-row gap-6">
                    <!-- 計算類型選擇 -->
                    <div class="flex-1">
                        <div class="flex flex-col sm:flex-row gap-3 items-start sm:items-center">
                            <label class="block text-sm font-medium text-gray-700 w-20">
                                計算類型 <span class="text-red-500">*</span>
                            </label>
                            <div class="flex-1 flex flex-wrap gap-4" id="calcTypeContainer">
                                <label class="inline-flex items-center cursor-pointer">
                                    <input 
                                        type="radio" 
                                        name="calcType" 
                                        value="fall" 
                                        class="sr-only peer"
                                    >
                                    <div class="w-5 h-5 border border-gray-300 rounded-full peer peer-checked:border-primary peer-checked:bg-primary flex items-center justify-center transition-all">
                                        <div class="w-3 h-3 bg-white rounded-full scale-0 peer-checked:scale-100 transition-transform"></div>
                                    </div>
                                    <span class="ml-2 text-gray-700">回跌位</span>
                                </label>
                                
                                <label class="inline-flex items-center cursor-pointer">
                                    <input 
                                        type="radio" 
                                        name="calcType" 
                                        value="rise" 
                                        class="sr-only peer"
                                    >
                                    <div class="w-5 h-5 border border-gray-300 rounded-full peer peer-checked:border-primary peer-checked:bg-primary flex items-center justify-center transition-all">
                                        <div class="w-3 h-3 bg-white rounded-full scale-0 peer-checked:scale-100 transition-transform"></div>
                                    </div>
                                    <span class="ml-2 text-gray-700">回升位</span>
                                </label>
                            </div>
                            <p id="calcTypeError" class="text-red-500 text-xs hidden w-full mt-1">請選擇計算類型</p>
                        </div>
                    </div>
                    
                    <!-- 計算對象選擇 -->
                    <div class="flex-1">
                        <div class="flex flex-col sm:flex-row gap-3 items-start sm:items-center">
                            <label class="block text-sm font-medium text-gray-700 w-20">
                                計算對象
                            </label>
                            <div class="flex-1 flex flex-wrap gap-4">
                                <label class="inline-flex items-center cursor-pointer">
                                    <input 
                                        type="radio" 
                                        name="calcTarget" 
                                        value="stock" 
                                        checked 
                                        class="sr-only peer"
                                    >
                                    <div class="w-5 h-5 border border-gray-300 rounded-full peer peer-checked:border-primary peer-checked:bg-primary flex items-center justify-center transition-all">
                                        <div class="w-3 h-3 bg-white rounded-full scale-0 peer-checked:scale-100 transition-transform"></div>
                                    </div>
                                    <span class="ml-2 text-gray-700">股價</span>
                                </label>
                                
                                <label class="inline-flex items-center cursor-pointer">
                                    <input 
                                        type="radio" 
                                        name="calcTarget" 
                                        value="index" 
                                        class="sr-only peer"
                                    >
                                    <div class="w-5 h-5 border border-gray-300 rounded-full peer peer-checked:border-primary peer-checked:bg-primary flex items-center justify-center transition-all">
                                        <div class="w-3 h-3 bg-white rounded-full scale-0 peer-checked:scale-100 transition-transform"></div>
                                    </div>
                                    <span class="ml-2 text-gray-700">指數</span>
                                </label>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 計算按鈕 -->
                <div class="pt-2">
                    <button 
                        id="calculateBtn" 
                        class="w-full bg-primary hover:bg-primary/90 text-white font-medium py-2 px-4 rounded-lg transition-colors btn-effect flex items-center justify-center gap-2"
                    >
                        <span class="icon icon-calculator"></span>
                        <span>計算結果</span>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- 結果顯示區域 -->
        <div id="resultContainer" class="bg-white rounded-xl p-6 md:p-8 card-shadow mb-6 hidden">
            <h2 class="text-xl font-semibold mb-4 pb-2 border-b border-gray-200">計算結果</h2>
            <div id="resultContent" class="whitespace-pre-line text-gray-700 leading-relaxed mb-6"></div>
            <button 
                id="copyBtn" 
                class="w-full bg-secondary hover:bg-secondary/90 text-white font-medium py-2 px-4 rounded-lg transition-colors btn-effect flex items-center justify-center gap-2"
            >
                <span class="icon icon-copy"></span>
                <span>複製結果</span>
            </button>
            <p id="copyMessage" class="text-center mt-2 text-green-600 text-sm hidden">
                <span class="icon icon-check-circle"></span> 已複製到剪貼簿
            </p>
        </div>
        
        <!-- 頁腳信息 -->
        <footer class="text-center text-gray-500 text-sm mt-12">
            <p>© 2025 費波南希數列計算工具 | <a href='https://snsim.futunn.com/share/group/688tS?lang=zh-hk' target='_blank'>由 【富途 【發哥免費指標王】 編寫免費分享。</a></p>
        </footer>
    </div>

    <script>
        // DOM元素
        const highInput = document.getElementById('high');
        const lowInput = document.getElementById('low');
        const calculateBtn = document.getElementById('calculateBtn');
        const resultContainer = document.getElementById('resultContainer');
        const resultContent = document.getElementById('resultContent');
        const copyBtn = document.getElementById('copyBtn');
        const copyMessage = document.getElementById('copyMessage');
        const highError = document.getElementById('highError');
        const lowError = document.getElementById('lowError');
        const calcTypeError = document.getElementById('calcTypeError');
        const highCurrencySymbol = document.getElementById('highCurrencySymbol');
        const lowCurrencySymbol = document.getElementById('lowCurrencySymbol');
        const calcTypeContainer = document.getElementById('calcTypeContainer');
        
        // 費波南希比率
        const ratios = [0.236, 0.382, 0.500, 0.618, 1.000, 1.618];
        
        // 更新貨幣符號顯示
        function updateCurrencySymbols() {
            const isStock = document.querySelector('input[name="calcTarget"][value="stock"]').checked;
            if (isStock) {
                highCurrencySymbol.textContent = '$';
                lowCurrencySymbol.textContent = '$';
            } else {
                highCurrencySymbol.textContent = '';
                lowCurrencySymbol.textContent = '';
            }
        }
        
        // 輸入驗證函數 - 只在點擊計算按鈕時調用
        function validateInputs() {
            let isValid = true;
            const highValue = parseFloat(highInput.value);
            const lowValue = parseFloat(lowInput.value);
            const selectedCalcType = document.querySelector('input[name="calcType"]:checked');
            
            // 重置所有錯誤提示
            highError.classList.add('hidden');
            lowError.classList.add('hidden');
            calcTypeError.classList.add('hidden');
            highInput.classList.remove('border-red-500');
            lowInput.classList.remove('border-red-500');
            calcTypeContainer.classList.remove('bg-red-50', 'p-2', 'rounded-lg');
            
            // 驗證計算類型
            if (!selectedCalcType) {
                calcTypeError.classList.remove('hidden');
                calcTypeContainer.classList.add('bg-red-50', 'p-2', 'rounded-lg');
                isValid = false;
            }
            
            // 驗證最高點
            if (isNaN(highValue) || highInput.value.trim() === '') {
                highError.textContent = '請輸入有效的數值（整數或小數）';
                highError.classList.remove('hidden');
                highInput.classList.add('border-red-500');
                isValid = false;
            }
            
            // 驗證最低點
            if (isNaN(lowValue) || lowInput.value.trim() === '') {
                lowError.textContent = '請輸入有效的數值（整數或小數）';
                lowError.classList.remove('hidden');
                lowInput.classList.add('border-red-500');
                isValid = false;
            }
            
            // 驗證最高點大於最低點
            if (isValid && highValue <= lowValue) {
                highError.textContent = '最高點必須大於最低點';
                highError.classList.remove('hidden');
                highInput.classList.add('border-red-500');
                isValid = false;
            }
            
            return isValid;
        }
        
        // 計算回跌位置
        function calculateFall(high, low, isStock) {
            const totalRise = high - low;
            const currencySymbol = isStock ? '$' : '';
            let result = `利用 富途 【發哥免費指標王】 的 【費波南希數列】 計算程式，【計算回跌位置】 結果如下：\n`;
            result += `【最高點】： ${currencySymbol}${high.toFixed(2)}\n`;
            result += `【最低點】： ${currencySymbol}${low.toFixed(2)}\n`;
            result += `【總升幅】： ${currencySymbol}${high.toFixed(2)} - ${currencySymbol}${low.toFixed(2)} = ${currencySymbol}${totalRise.toFixed(2)}\n`;
            
            ratios.forEach(ratio => {
                const value = high - totalRise * ratio;
                result += `回跌 【總升幅】 的 ${ratio.toFixed(3)}， 即： ${currencySymbol}${value.toFixed(2)} （${currencySymbol}${high.toFixed(2)} - ${currencySymbol}${totalRise.toFixed(2)}*${ratio.toFixed(3)}）\n`;
            });
            
            result += `\n誠邀請你 免費加入群聊 【發哥免費指標王交流區】股票交流群組，分享更多免費指標！\n`;
            result += `https://snsim.futunn.com/share/group/688tS?lang=zh-hk`;
            
            return result;
        }
        
        // 計算回升位置
        function calculateRise(high, low, isStock) {
            const totalFall = high - low;
            const currencySymbol = isStock ? '$' : '';
            let result = `利用 富途 【發哥免費指標王】 的 【費波南希數列】 計算程式，【計算回升位置】 結果如下：\n`;
            result += `【最高點】： ${currencySymbol}${high.toFixed(2)}\n`;
            result += `【最低點】： ${currencySymbol}${low.toFixed(2)}\n`;
            result += `【總跌幅】： ${currencySymbol}${high.toFixed(2)} - ${currencySymbol}${low.toFixed(2)} = ${currencySymbol}${totalFall.toFixed(2)}\n`;
            
            ratios.forEach(ratio => {
                const value = low + totalFall * ratio;
                result += `回升 【總跌幅】 的 ${ratio.toFixed(3)}， 即： ${currencySymbol}${value.toFixed(2)} （${currencySymbol}${low.toFixed(2)} + ${currencySymbol}${totalFall.toFixed(2)}*${ratio.toFixed(3)}）\n`;
            });
            
            result += `\n誠邀請你 免費加入群聊 【發哥免費指標王交流區】股票交流群組，分享更多免費指標！\n`;
            result += `https://snsim.futunn.com/share/group/688tS?lang=zh-hk`;
            
            return result;
        }
        
        // 計算按鈕點擊事件
        calculateBtn.addEventListener('click', () => {
            if (validateInputs()) {
                const high = parseFloat(highInput.value);
                const low = parseFloat(lowInput.value);
                const calcType = document.querySelector('input[name="calcType"]:checked').value;
                const isStock = document.querySelector('input[name="calcTarget"][value="stock"]').checked;
                
                let result;
                if (calcType === 'fall') {
                    result = calculateFall(high, low, isStock);
                } else {
                    result = calculateRise(high, low, isStock);
                }
                
                // 顯示結果
                resultContent.textContent = result;
                resultContainer.classList.remove('hidden');
                
                // 平滑滾動到結果區域
                resultContainer.scrollIntoView({ behavior: 'smooth', block: 'start' });
            } else {
                // 如果驗證失敗，顯示提示alert
                alert('請選擇計算類型並確保輸入正確的數值');
            }
        });
        
        // 複製按鈕點擊事件
        copyBtn.addEventListener('click', () => {
            const textToCopy = resultContent.textContent;
            
            navigator.clipboard.writeText(textToCopy).then(() => {
                // 顯示複製成功消息
                copyMessage.classList.remove('hidden');
                setTimeout(() => {
                    copyMessage.classList.add('hidden');
                }, 2000);
                
                // 按鈕動畫效果
                copyBtn.classList.add('bg-green-700');
                setTimeout(() => {
                    copyBtn.classList.remove('bg-green-700');
                }, 300);
            }).catch(err => {
                console.error('複製失敗: ', err);
                alert('複製失敗，請手動複製。');
            });
        });
        
        // 計算對象切換事件
        document.querySelectorAll('input[name="calcTarget"]').forEach(radio => {
            radio.addEventListener('change', updateCurrencySymbols);
        });
        
        // 實時輸入格式化（僅格式化，不顯示錯誤）
        highInput.addEventListener('input', () => {
            // 只允許數字和小數點
            highInput.value = highInput.value.replace(/[^0-9.]/g, '');
            // 只允許一個小數點
            const parts = highInput.value.split('.');
            if (parts.length > 2) {
                highInput.value = parts[0] + '.' + parts.slice(1).join('');
            }
        });
        
        lowInput.addEventListener('input', () => {
            // 只允許數字和小數點
            lowInput.value = lowInput.value.replace(/[^0-9.]/g, '');
            // 只允許一個小數點
            const parts = lowInput.value.split('.');
            if (parts.length > 2) {
                lowInput.value = parts[0] + '.' + parts.slice(1).join('');
            }
        });
    </script>
</body>
</html>
    
