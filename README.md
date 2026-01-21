<input type="text" id="usernameInput" placeholder="اسم المستخدم">

<button onclick="login()">دخول</button>

<script>// وظيفة استلام المكافأة
function claimReward() {
    alert("تم استلام مكافأة التسجيل اليومية بنجاح! +10 DZD");
    // هنا يمكنك مستقبلاً ربط الكود لتحديث الرصيد في قاعدة البيانات
}

// وظيفة استئجار المعدات
function rentMachine(name, price) {
    if(confirm("هل تريد تأجير " + name + " مقابل " + price + " DZD؟")) {
        alert("عذراً، رصيدك الحالي غير كافٍ. يرجى شحن الحساب أولاً.");
    }
}

function login() {
    // 1. الحصول على الاسم من الحقل
    var name = document.getElementById("usernameInput").value;
    
    if (name === "") {
        alert("يرجى إدخال اسم المستخدم");
        return;
    }

    // 2. حفظ الاسم في ذاكرة المتصفح
    localStorage.setItem("user_name", name);
    
    // 3. الانتقال إلى لوحة التحكم
    window.location.href = "dashboard.html";
}
</script>
<button onclick="window.location.href='dashboard.html'">دخول</button>!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>لوحة التحكم الذكية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
    <style>body { font-family: 'Cairo', sans-serif; background-color: #f4f7fe; }</style>
</head>
<body class="pb-24">

    <div class="bg-white p-4 flex justify-between items-center shadow-sm">
        <div class="flex items-center gap-2">
            <div class="w-10 h-10 bg-blue-600 rounded-full flex items-center justify-center text-white font-bold">U</div>
            <h1 class="text-xl font-bold text-gray-800">UNITREE</h1>
        </div>
        <div class="relative">
            <span class="absolute -top-1 -right-1 bg-red-500 w-2 h-2 rounded-full"></span>
            <svg class="w-6 h-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"></path></svg>
        </div>
    </div>

    <div class="p-4">
        <div class="bg-gradient-to-r from-blue-700 to-blue-500 rounded-3xl p-6 text-white relative overflow-hidden shadow-lg">
            <h2 class="text-lg font-bold mb-1">شريكك الموثوق في الحلول الذكية</h2>
            <p class="text-xs opacity-80">ابدأ العمل والربح اليوم!</p>
            <div class="mt-4 bg-white/20 backdrop-blur-md inline-block px-4 py-2 rounded-xl text-xs">من نحن؟ معلومات عن التطبيق</div>
            <div class="absolute -left-4 -bottom-4 opacity-20 text-9xl">🤖</div>
        </div>
    </div>

    <div class="px-4 mb-6">
        <div class="bg-white rounded-3xl p-6 shadow-sm border border-gray-50">
            <div class="flex justify-between items-center mb-4">
                <span class="text-gray-800 font-bold text-lg">الأصول</span>
                <span class="bg-blue-50 text-blue-600 text-xs px-3 py-1 rounded-lg font-bold">رصيد الحساب</span>
            </div>
            <div class="flex items-baseline gap-1">
                <span class="text-blue-600 font-bold text-xl font-mono">DZD</span>
                <span class="text-4xl font-black text-gray-900 tracking-tighter">510,00</span>
            </div>

            <div class="grid grid-cols-3 gap-4 mt-8">
                <button class="flex flex-col items-center gap-2">
                    <div class="w-14 h-14 bg-red-50 rounded-2xl flex items-center justify-center text-2xl shadow-sm border border-red-100">📥</div>
                    <span class="text-xs font-bold text-gray-600">شحن</span>
                </button>
                <button class="flex flex-col items-center gap-2">
                    <div class="w-14 h-14 bg-blue-50 rounded-2xl flex items-center justify-center text-2xl shadow-sm border border-blue-100">📤</div>
                    <span class="text-xs font-bold text-gray-600">سحب</span>
                </button>
                <button class="flex flex-col items-center gap-2">
                    <div class="w-14 h-14 bg-blue-50 rounded-2xl flex items-center justify-center text-2xl shadow-sm border border-blue-100">🎧</div>
                    <span class="text-xs font-bold text-gray-600">خدمة العملاء</span>
                </button>
            </div>
        </div>
    </div>

    <div class="px-4 grid grid-cols-2 gap-4">
        <div class="bg-green-50/50 p-4 rounded-3xl border border-green-100 flex flex-col gap-2">
            <div class="w-10 h-10 bg-green-100 rounded-xl flex items-center justify-center text-xl">📅</div>
            <span class="text-sm font-bold text-gray-700 leading-tight">مكافأة التسجيل اليومي</span>
        </div>
        <div class="bg-purple-50/50 p-4 rounded-3xl border border-purple-100 flex flex-col gap-2">
            <div class="w-10 h-10 bg-purple-100 rounded-xl flex items-center justify-center text-xl">🎁</div>
            <span class="text-sm font-bold text-gray-700 leading-tight">علبة هدايا</span>
        </div>
    </div>

    <div class="fixed bottom-0 left-0 right-0 bg-white border-t border-gray-100 px-6 py-3 flex justify-between items-center shadow-[0_-5px_20px_rgba(0,0,0,0.05)]">
        <div class="flex flex-col items-center gap-1 text-blue-600">
            <span class="text-xl">🏠</span>
            <span class="text-[10px] font-bold">الرئيسية</span>
        </div>
        <div class="flex flex-col items-center gap-1 text-gray-400">
            <span class="text-xl">⚙️</span>
            <span class="text-[10px] font-bold">المعدات</span>
        </div>
        <div class="flex flex-col items-center gap-1 text-gray-400">
            <span class="text-xl">👥</span>
            <span class="text-[10px] font-bold">دعوة</span>
        </div>
        <div class="flex flex-col items-center gap-1 text-gray-400">
            <span class="text-xl">👤</span>
            <span class="text-[10px] font-bold">حسابي</span>
        </div>
    </div>
<div class="grid grid-cols-2 gap-4 p-4">
    <div class="bg-white p-4 rounded-2xl shadow-sm border border-gray-100 text-center">
        <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-2 text-2xl">🎁</div>
        <h4 class="text-sm font-bold text-gray-800">مكافأة التسجيل</h4>
        <p class="text-xs text-blue-600 font-bold mt-1">DZD 10.00</p>
        <button class="bg-blue-600 text-white text-xs px-4 py-1 rounded-full mt-2">استلام</button>
    </div>

    <div class="bg-white p-4 rounded-2xl shadow-sm border border-gray-100 text-center">
        <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-2 text-2xl">📦</div>
        <h4 class="text-sm font-bold text-gray-800">علبة الهدايا</h4>
        <p class="text-xs text-gray-400 mt-1">أدخل الكود</p>
        <button class="bg-gray-100 text-gray-600 text-xs px-4 py-1 rounded-full mt-2">فتح</button>
    </div>
</div>

<div class="px-4 mb-20">
    <h3 class="font-bold text-gray-800 mb-3">المعدات الذكية المتوفرة</h3>
    <div class="bg-white p-3 rounded-2xl shadow-sm flex items-center gap-4 border border-gray-100">
        <img src="https://via.placeholder.com/80" class="rounded-xl bg-gray-50" alt="Robot">
        <div class="flex-1">
            <h4 class="text-sm font-bold">روبوت الفئة الأولى (G1)</h4>
            <p class="text-xs text-gray-500">الدخل اليومي: DZD 150</p>
            <div class="flex justify-between items-center mt-2">
                <span class="text-blue-600 font-bold text-sm">DZD 2,000</span>
                <button class="bg-blue-600 text-white text-xs px-4 py-1 rounded-lg">إيجار</button>
            </div>
        </div>
    </div>
</div>

</body>
</html><script>
// دالة لإظهار رسالة عند الضغط على الأزرار
function showAction(type) {
    let message = "";
    if(type === 'deposit') message = "جارٍ تحويلك إلى بوابة الشحن...";
    if(type === 'withdraw') message = "عذراً، يجب أن يكون رصيدك 2000 DZD على الأقل للسحب.";
    
    // إظهار تنبيه بسيط للمستخدم
    alert(message);
}
</script>

