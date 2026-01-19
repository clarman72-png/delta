# delta
مشروع منصة  
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
            <h1 class="text-2xl font-bold text-blue-900 mb-2">أهلاً بك في منصتك</h1>
            <p class="text-gray-400 text-sm mb-6">يرجى تسجيل الدخول للبدء</p>
            <input type="text" id="username" placeholder="اسم المستخدم" class="w-full p-4 bg-gray-50 border rounded-2xl mb-4 outline-none focus:ring-2 focus:ring-blue-500 text-center">
            <button onclick="startApp()" class="w-full bg-blue-600 text-white py-4 rounded-2xl font-bold shadow-lg hover:bg-blue-700 transition">دخول</button>
        </div>
    </div>

    <div id="dashboard" class="hidden">
        <div class="bg-blue-600 p-8 text-white rounded-b-[40px] shadow-lg">
            <div class="flex justify-between items-center mb-6">
                <span class="text-sm opacity-80">مرحباً، <b id="user-name"></b></span>
                <button onclick="location.reload()" class="bg-white/20 p-2 rounded-lg text-xs">خروج</button>
            </div>
            <div class="text-center">
                <p class="text-xs opacity-70 mb-1">الرصيد الكلي بالدينار</p>
                <h2 class="text-4xl font-bold tracking-tighter" id="balance">250,000.00 د.ج</h2>
            </div>
        </div>

        <div class="p-6">
            <div class="bg-white p-6 rounded-3xl shadow-sm border mb-6">
                <h3 class="font-bold text-gray-700 mb-4 flex items-center">
                    <span class="ml-2">💰</span> محول الدولار / دينار
                </h3>
                <div class="space-y-4">
                    <div class="relative">
                        <input type="number" id="usd" oninput="calculateDzd()" placeholder="المبلغ بالدولار $" class="w-full p-4 bg-gray-50 rounded-2xl font-bold text-center border-2 focus:border-blue-400 outline-none">
                    </div>
                    <div class="text-center font-bold text-blue-500">⇵</div>
                    <div class="relative">
                        <input type="number" id="dzd" oninput="calculateUsd()" placeholder="المبلغ بالدينار دج" class="w-full p-4 bg-gray-50 rounded-2xl font-bold text-center border-2 focus:border-blue-400 outline-none">
                    </div>
                </div>
                <p class="text-[10px] text-gray-400 mt-4 text-center">سعر الصرف المعتمد: 1 دولار = 215 دينار جزائري</p>
            </div>
        </div>
    </div>

    <script>
        const RATE = 215;

        function startApp() {
            const name = document.getElementById('username').value;
            if(name === "") return alert("من فضلك اكتب اسمك");
            
            document.getElementById('user-name').innerText = name;
            document.getElementById('login-page').classList.add('hidden');
            document.getElementById('dashboard').classList.remove('hidden');
        }

        function calculateDzd() {
            const usd = document.getElementById('usd').value;
            document.getElementById('dzd').value = (usd * RATE).toFixed(2);
        }

        function calculateUsd() {
            const dzd = document.getElementById('dzd').value;
            document.getElementById('usd').value = (dzd / RATE).toFixed(2);
        }
    </script>
</body>
</html>
