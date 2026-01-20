<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة التبادل المالي</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap" rel="stylesheet">
    <style>body { font-family: 'Cairo', sans-serif; }</style>
</head>
<body class="bg-slate-50 min-h-screen">
    <div id="login-page" class="flex flex-col items-center justify-center min-h-screen p-6">
        <div class="bg-white p-8 rounded-3xl shadow-xl w-full max-w-sm border-t-8 border-blue-600 text-center">
            <h1 class="text-2xl font-bold text-blue-900 mb-2">منصة التبادل</h1>
            <p class="text-gray-400 text-sm mb-6">سجل دخولك الآن</p>
            <input type="text" id="username" placeholder="اسم المستخدم" class="w-full p-4 bg-gray-50 border rounded-2xl mb-4 text-center outline-none focus:ring-2 focus:ring-blue-500">
            <button onclick="startApp()" class="w-full bg-blue-600 text-white py-4 rounded-2xl font-bold shadow-lg">دخول</button>
        </div>
    </div>

    <div id="dashboard" class="hidden">
        <div class="bg-blue-600 p-8 text-white rounded-b-[40px] shadow-lg text-center">
            <p class="text-xs opacity-70 mb-1">الرصيد المتوفر</p>
            <h2 class="text-4xl font-bold">250,000.00 د.ج</h2>
        </div>
        <div class="p-6">
            <div class="bg-white p-6 rounded-3xl shadow-sm border text-center">
                <h3 class="font-bold mb-4">محول العملات (1$ = 215 دج)</h3>
                <input type="number" id="usd" oninput="document.getElementById('dzd').value = (this.value * 215).toFixed(2)" placeholder="المبلغ بالدولار $" class="w-full p-4 bg-gray-50 rounded-2xl text-center border-2 mb-4">
                <input type="number" id="dzd" placeholder="المبلغ بالدينار دج" class="w-full p-4 bg-gray-50 rounded-2xl text-center border-2">
            </div>
        </div>
    </div>

    <script>
        function startApp() {
            if(document.getElementById('username').value === "") return alert("اكتب اسمك أولاً");
            document.getElementById('login-page').className = 'hidden';
            document.getElementById('dashboard').className = 'block';
        }
    </script>
</body>
</html>
