<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ระบบนัดหมายวันนำรถเข้าตรวจพิสูจน์</title>

    <script src="https://cdn.tailwindcss.com"></script>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@400;700&display=swap" rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
    <script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
    <script src="https://npmcdn.com/flatpickr/dist/l10n/th.js"></script> <script charset="utf-8" src="https://static.line-scdn.net/liff/edge/2/sdk.js"></script>

    <style>
        /* กำหนด font Sarabun เป็น default */
        body {
            font-family: 'Sarabun', sans-serif;
        }
        /* ซ่อนลูกศรของ input[type=number] */
        input[type=number]::-webkit-inner-spin-button,
        input[type=number]::-webkit-outer-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        input[type=number] {
            -moz-appearance: textfield;
        }
    </style>

    <script>
        // กำหนดค่า Tailwind ให้ใช้ font Sarabun
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Sarabun', 'sans-serif'],
                        serif: ['Sarabun', 'serif'],
                    },
                },
            },
        }
    </script>
</head>
<body class="bg-gray-100 text-[#15244A]">

    <div class="container mx-auto max-w-4xl p-4 md:p-8">

        <header class="mb-6">
        <img
            src="https://lh3.googleusercontent.com/d/1R1n9Z79Md7puGNBLUkRVDOLuEB7gyjzj"
            alt="Logo"
            class="logo-large mx-auto mb-0 mt-2 object-contain h-40"> <div class="bg-[#7F141F] text-white p-4 rounded-t-lg">
                <h1 class="text-xl md:text-2xl font-bold text-center">ระบบนัดหมายวันนำรถเข้าตรวจพิสูจน์</h1>
            </div>
            <div class="bg-white p-4 rounded-b-lg shadow-md text-center">
                <h2 class="text-lg md:text-xl font-semibold">กลุ่มงานตรวจทางเคมี ฟิสิกส์</h2>
                <h3 class="text-md md:text-lg">ศูนย์พิสูจน์หลักฐาน 3</h3>
            </div>
        </header>

        <form id="bookingForm" class="bg-white p-6 md:p-8 rounded-lg shadow-lg space-y-6">

            <fieldset class="border-b-2 border-gray-200 pb-6">
                <legend class="text-lg font-semibold text-[#15244A] mb-4">ข้อมูลทั่วไปผู้ขอตรวจพิสูจน์</legend>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <label for="firstName" class="block text-sm font-medium mb-1">ชื่อ *</label>
                        <input type="text" id="firstName" name="firstName" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="lastName" class="block text-sm font-medium mb-1">สกุล *</label>
                        <input type="text" id="lastName" name="lastName" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="phone" class="block text-sm font-medium mb-1">เบอร์โทรศัพท์ * (9-10 หลัก)</label>
                        <input type="text" inputmode="numeric" id="phone" name="phone" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div class="md:col-span-2">
                        <label class="block text-sm font-medium mb-1">สถานะของผู้ขอตรวจพิสูจน์ *</label>
                        <div class="flex gap-4 mt-2">
                            <label class="flex items-center">
                                <input type="radio" name="status" value="เจ้าของรถ" class="text-[#7F141F] focus:ring-[#7F141F]" required>
                                <span class="ml-2">เจ้าของรถ</span>
                            </label>
                            <label class="flex items-center">
                                <input type="radio" id="statusOther" name="status" value="ไม่ใช่เจ้าของรถ" class="text-[#7F141F] focus:ring-[#7F141F]">
                                <span class="ml-2">ไม่ใช่เจ้าของรถ</span>
                            </label>
                        </div>
                    </div>
                </div>
            </fieldset>

            <fieldset class="border-b-2 border-gray-200 pb-6">
                <legend class="text-lg font-semibold text-[#15244A] mb-4">ข้อมูลของรถที่ขอตรวจพิสูจน์</legend>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <label for="carType" class="block text-sm font-medium mb-1">ชนิดของรถ *</label>
                        <select id="carType" name="carType" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                            <option value="">-- กรุณาเลือก --</option>
                            <option value="รถยนต์เก๋ง">รถยนต์เก๋ง</option>
                            <option value="รถยนต์นั่ง">รถยนต์นั่ง</option>
                            <option value="รถยนต์กระบะ">รถยนต์กระบะ</option>
                            <option value="รถจักรยานยนต์">รถจักรยานยนต์</option>
                            <option value="รถยนต์ตู้">รถยนต์ตู้</option>
                            <option value="รถบรรทุก">รถบรรทุก</option>
                            <option value="รถโดยสาร">รถโดยสาร</option>
                            <option value="รถหัวลาก">รถหัวลาก</option>
                            <option value="รถพ่วง">รถพ่วง</option>
                            <option value="อื่น ๆ">อื่น ๆ</option>
                        </select>
                    </div>
                    <div id="carTypeOtherWrapper" class="hidden">
                        <label for="carTypeOther" class="block text-sm font-medium mb-1">ระบุชนิดของรถ *</label>
                        <input type="text" id="carTypeOther" name="carTypeOther" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]">
                    </div>
                    <div>
                        <label for="carColor" class="block text-sm font-medium mb-1">สี *</label>
                        <input type="text" id="carColor" name="carColor" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="carMake" class="block text-sm font-medium mb-1">ยี่ห้อ *</label>
                        <input type="text" id="carMake" name="carMake" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="carModel" class="block text-sm font-medium mb-1">รุ่น *</label>
                        <input type="text" id="carModel" name="carModel" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="licensePlate" class="block text-sm font-medium mb-1">แผ่นป้ายทะเบียนหมายเลข *</label>
                        <input type="text" id="licensePlate" name="licensePlate" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                    <div>
                        <label for="province" class="block text-sm font-medium mb-1">จังหวัด *</label>
                        <input type="text" id="province" name="province" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F]" required>
                    </div>
                </div>
            </fieldset>

            <fieldset class="border-b-2 border-gray-200 pb-6">
                <legend class="text-lg font-semibold text-[#15244A] mb-4">ต้องการตรวจพิสูจน์ (เลือกได้หลายรายการ)</legend>
                <div class="space-y-2">
                    <label class="flex items-center">
                        <input type="checkbox" name="inspectionType" value="ตรวจพิสูจน์เลขตัวรถ" class="text-[#7F141F] focus:ring-[#7F141F] rounded">
                        <span class="ml-2">ตรวจพิสูจน์เลขตัวรถ</span>
                    </label>
                    <label class="flex items-center">
                        <input type="checkbox" name="inspectionType" value="ตรวจพิสูจน์เลขเครื่องยนต์" class="text-[#7F141F] focus:ring-[#7F141F] rounded">
                        <span class="ml-2">ตรวจพิสูจน์เลขเครื่องยนต์</span>
                    </label>
                    <label class="flex items-center">
                        <input type="checkbox" name="inspectionType" value="การเปลี่ยนแปลงสีรถ" class="text-[#7F141F] focus:ring-[#7F141F] rounded">
                        <span class="ml-2">การเปลี่ยนแปลงสีรถ</span>
                    </label>
                    <label class="flex items-center">
                        <input type="checkbox" name="inspectionType" value="การตัดต่อตัวถัง" class="text-[#7F141F] focus:ring-[#7F141F] rounded">
                        <span class="ml-2">การตัดต่อตัวถัง</span>
                    </label>
                </div>
            </fieldset>

            <fieldset class="border-b-2 border-gray-200 pb-6">
                <legend class="text-lg font-semibold text-[#15244A] mb-4">วันนำรถเข้าตรวจพิสูจน์</legend>
                <p class="text-red-600 font-semibold mb-4 text-sm">
                    กรุณาเลือกวันที่ต้องการนำรถเข้าตรวจพิสูจน์ 3 อันดับ โดยจะต้องนำรถเข้าตรวจพิสูจน์ ณ ศูนย์พิสูจน์หลักฐาน 3 เวลา 09:00 น. ของแต่ละวันในวันจันทร์ - ศุกร์ ยกเว้นวันหยุดนักขัตฤกษ์
                </p>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div>
                        <label for="date1" class="block text-sm font-medium mb-1">อันดับที่ 1 *</label>
                        <input type="text" id="date1" name="date1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F] bg-white" placeholder="เลือกวันที่" readonly required>
                    </div>
                    <div>
                        <label for="date2" class="block text-sm font-medium mb-1">อันดับที่ 2 *</label>
                        <input type="text" id="date2" name="date2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F] bg-white" placeholder="เลือกวันที่" readonly required>
                    </div>
                    <div>
                        <label for="date3" class="block text-sm font-medium mb-1">อันดับที่ 3 *</label>
                        <input type="text" id="date3" name="date3" class="w-full p-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-[#7F141F] bg-white" placeholder="เลือกวันที่" readonly required>
                    </div>
                </div>
            </fieldset>

            <fieldset>
                <legend class="text-lg font-semibold text-[#15244A] mb-4">แนบเอกสาร</legend>
                <label for="fileUpload" class="block text-sm font-medium mb-1">กรุณาแนบรูปหนังสือนำส่งและเอกสารที่เกี่ยวข้องจากขนส่ง (ไม่บังคับ)</label>
                <input type="file" id="fileUpload" name="fileUpload" class="w-full p-2 border border-gray-300 rounded-md file:mr-4 file:py-2 file:px-4 file:rounded-md file:border-0 file:text-sm file:font-semibold file:bg-[#15244A] file:text-white hover:file:bg-[#7F141F]" multiple accept="image/*">
                <div id="fileList" class="mt-2 text-sm text-gray-600"></div>
            </fieldset>

            <div class="mt-6">
                <button type="submit" id="submitButton" class="w-full bg-[#7F141F] text-white p-3 rounded-lg font-bold text-lg hover:bg-[#a12f3e] transition duration-300">
                    ยืนยันการนัดหมาย
                </button>
            </div>
        </form>

        <footer class="text-center text-gray-500 text-sm mt-8">
            Copyright © <span id="currentYear"></span>, กลุ่มงานตรวจทางเคมี ฟิสิกส์ ศูนย์พิสูจน์หลักฐาน 3
        </footer>
    </div>

    <script>
        // --- JavaScript Logic ---

        // 1.) ID จาก LINE LIFF
        const LIFF_ID = '2008403863-PnBQ2roz';
        // 2.) URL ของ Google Apps Script (ต้องนำมาใส่หลัง Deploy)
        const GAS_WEB_APP_URL = 'https://script.google.com/macros/s/AKfycbwg2_ztM2hlmKqit7WAt7DCG9ymDd9ZRfnnP-cfdjxTcMjiMQTL18XPdkTHfRTvzMqk/exec'; // <--- !!! ต้องเปลี่ยนตรงนี้ !!!

        let liffUserId = null;

        // ฟังก์ชันสำหรับจัดรูปแบบวันที่เป็น "วันพุธ ที่ 12 มกราคม พ.ศ. 2538"
        function formatDateThaiBE(date) {
            const thaiDate = new Date(date.getTime());
            const yearBE = thaiDate.getFullYear() + 543;
            
            const options = {
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric',
                timeZone: 'Asia/Bangkok'
            };
            
            let formatted = new Intl.DateTimeFormat('th-TH-u-ca-buddhist', options).format(thaiDate);
            // แทนที่ปี ค.ศ. ด้วย พ.ศ.
            formatted = formatted.replace(String(date.getFullYear()), String(yearBE));
            // บาง browser อาจจะแสดง พ.ศ. อยู่แล้ว
            if (!formatted.includes(String(yearBE))) {
                formatted = formatted.replace(/\d{4}$/, yearBE);
            }
            
            return formatted;
        }

        // ฟังก์ชันอ่านไฟล์เป็น Base64
        function readFileAsBase64(file) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                reader.onload = () => {
                    // แยกส่วน base64 data
                    const base64String = reader.result.split(',')[1];
                    resolve({
                        filename: file.name,
                        mimeType: file.type,
                        base64String: base64String
                    });
                };
                reader.onerror = error => reject(error);
                reader.readAsDataURL(file);
            });
        }

        // --- เมื่อ DOM โหลดเสร็จ ---
        document.addEventListener('DOMContentLoaded', () => {
            // 1. Initialize LIFF
            liff.init({ liffId: LIFF_ID })
                .then(() => {
                    if (!liff.isLoggedIn()) {
                        Swal.fire({
                            icon: 'warning',
                            title: 'กรุณาเข้าสู่ระบบ',
                            text: 'ระบบนี้ต้องเข้าสู่ระบบ LINE ก่อนใช้งาน',
                            allowOutsideClick: false,
                        }).then(() => {
                            liff.login();
                        });
                    } else {
                        liff.getProfile()
                            .then(profile => {
                                liffUserId = profile.userId;
                                console.log('LIFF UserID:', liffUserId);
                            })
                            .catch(err => console.error('Get Profile Error', err));
                    }
                })
                .catch((err) => {
                    console.error('LIFF Init Error', err);
                    Swal.fire('เกิดข้อผิดพลาด', 'ไม่สามารถเชื่อมต่อกับ LINE LIFF ได้', 'error');
                });

            // 2. ตั้งค่า Footer ปีปัจจุบัน
            document.getElementById('currentYear').textContent = new Date().getFullYear();

            // 3. ตั้งค่า Date Pickers (Flatpickr)
            const dateInputs = ['date1', 'date2', 'date3'];
            const flatpickrInstances = {};

	// (Requirement 2) ฟังก์ชันตรวจสอบวันที่ซ้ำ [แก้ไข Timezone]
            function checkDateDuplicates(currentInstance) {
                const dates = {};
                let hasDuplicate = false;
                let duplicateDateStr = null; // ตัวแปรเก็บ Y-m-d ที่ซ้ำ

                // วนลูปเพื่อเก็บวันที่ทั้งหมดที่ถูกเลือก
                for (const id of dateInputs) {
                    const picker = flatpickrInstances[id];
                    
                    // ใช้ picker.input.value ซึ่งเก็บค่า "Y-m-d" โดยตรง
                    // (แทน .toISOString() ที่ทำให้วันที่เพี้ยน)
                    if (picker && picker.input.value) { 
                        const dateStr = picker.input.value; // e.g., "2025-11-12"
                        
                        if (dates[dateStr]) {
                            // ถ้าพบว่ามี key นี้อยู่แล้ว = ซ้ำ
                            hasDuplicate = true;
                            duplicateDateStr = dateStr; // e.g., "2025-11-12"
                            break;
                        }
                        dates[dateStr] = true; // เก็บวันที่นี้ไว้
                    }
                }

                // ถ้าพบว่าซ้ำ และมีการเรียกจาก instance ที่เพิ่งเลือก
                if (hasDuplicate && currentInstance) {
                    
                    // *** ส่วนที่แก้ไขการแสดงผล ***
                    // สร้าง Date object จาก string "Y-m-d" ที่ซ้ำ
                    // ด้วยวิธีที่ปลอดภัยจาก Timezone (ไม่ใช้ new Date("YYYY-MM-DD"))
                    const parts = duplicateDateStr.split('-').map(Number); // [2025, 11, 12]
                    const year = parts[0];
                    const monthIndex = parts[1] - 1; // เดือนใน JavaScript เริ่มจาก 0 (11 คือ พ.ย.)
                    const day = parts[2];
                    
                    // สร้างวันที่ใหม่โดยอิงตาม Local Timezone
                    const duplicateDateObj = new Date(year, monthIndex, day); 
                    
                    // แปลงเป็นข้อความภาษาไทย
                    const formattedDuplicateDate = formatDateThaiBE(duplicateDateObj);

                    Swal.fire({
                        icon: 'error',
                        title: 'วันที่ซ้ำกัน',
                        // แสดงผลวันที่ที่ถูกต้อง (เช่น "วันพุธ ที่ 12 พฤศจิกายน 2568")
                        text: `ท่านได้เลือก "${formattedDuplicateDate}" แล้ว กรุณาเลือกวันอื่น`,
                    });
                    
                    currentInstance.clear(); // ล้างค่าในช่องที่เพิ่งเลือก
                }
            }

            dateInputs.forEach(id => {
                flatpickrInstances[id] = flatpickr(`#${id}`, {
                    locale: 'th',
                    dateFormat: 'Y-m-d', // รูปแบบที่เก็บค่าจริง
                    altInput: true, // แสดง input อีกอันสำหรับ format ที่สวยงาม
                    altFormat: 'l ที่ j F พ.ศ. Y', // รูปแบบที่แสดง
                    minDate: 'today',
                    "disable": [
                        function(date) {
                            // ปิด เสาร์ (6) และ อาทิตย์ (0)
                            return (date.getDay() === 0 || date.getDay() === 6);
                        }
                    ],
                    onChange: function(selectedDates, dateStr, instance) {
                        // 1. จัดรูปแบบ พ.ศ. (เหมือนเดิม)
                        if (selectedDates.length > 0) {
                            const formattedDate = formatDateThaiBE(selectedDates[0]);
                            instance.altInput.value = formattedDate;
                        }
                        
                        // 2. (Requirement 2) ตรวจสอบวันที่ซ้ำทันที
                        setTimeout(() => checkDateDuplicates(instance), 0);
                    }
                });
            });


            // 4. Event Listeners
            const form = document.getElementById('bookingForm');
            const phoneInput = document.getElementById('phone');
            const statusOtherRadio = document.getElementById('statusOther');
            const carTypeSelect = document.getElementById('carType');
            const carTypeOtherWrapper = document.getElementById('carTypeOtherWrapper');
            const carTypeOtherInput = document.getElementById('carTypeOther');
            const fileUploadInput = document.getElementById('fileUpload');
            const fileListDiv = document.getElementById('fileList');

            // 5.1) ตรวจสอบเบอร์โทร
            phoneInput.addEventListener('input', () => {
                const phone = phoneInput.value;
                if (phone.length > 10) {
                    phoneInput.value = phone.slice(0, 10);
                }
            });

            // 5.1) แจ้งเตือน "ไม่ใช่เจ้าของรถ"
            statusOtherRadio.addEventListener('change', () => {
                if (statusOtherRadio.checked) {
                    Swal.fire({
                        icon: 'info',
                        title: 'ข้อควรทราบ',
                        text: 'ต้องมีหนังสือมอบอำนาจจากเจ้าของรถมาแสดงในวันตรวจพิสูจน์',
                    });
                }
            });

            // 5.2) ซ่อน/แสดง ช่อง "อื่น ๆ"
            carTypeSelect.addEventListener('change', () => {
                if (carTypeSelect.value === 'อื่น ๆ') {
                    carTypeOtherWrapper.classList.remove('hidden');
                    carTypeOtherInput.required = true;
                } else {
                    carTypeOtherWrapper.classList.add('hidden');
                    carTypeOtherInput.required = false;
                }
            });

            // 5.5) แสดงรายการไฟล์ที่เลือก
            fileUploadInput.addEventListener('change', () => {
                fileListDiv.innerHTML = '';
                if (fileUploadInput.files.length > 0) {
                    const list = document.createElement('ul');
                    list.className = 'list-disc list-inside';
                    Array.from(fileUploadInput.files).forEach(file => {
                        const li = document.createElement('li');
                        li.textContent = file.name;
                        list.appendChild(li);
                    });
                    fileListDiv.appendChild(list);
                }
            });


            // 6. & 7. (Requirement 4) แก้ไขการ Submit Form ให้มี Preview
            form.addEventListener('submit', async (e) => {
                e.preventDefault();

                // --- ตรวจสอบข้อมูลก่อนส่ง ---
                // 1. ตรวจสอบ LIFF UserID
                if (!liffUserId) {
                    Swal.fire('เกิดข้อผิดพลาด', 'ไม่พบข้อมูลผู้ใช้ LINE (LIFF UserID) กรุณาลองใหม่อีกครั้ง', 'error');
                    return;
                }

                // 2. ตรวจสอบเบอร์โทร
                const phone = phoneInput.value;
                if (phone.length < 9 || phone.length > 10) {
                    Swal.fire('เกิดข้อผิดพลาด', 'กรุณากรอกเบอร์โทรศัพท์ให้ถูกต้อง (9 – 10 หลัก)', 'error');
                    return;
                }
                
                // 3. ตรวจสอบว่าเลือกประเภทการตรวจอย่างน้อย 1
                const inspectionTypes = Array.from(document.querySelectorAll('input[name="inspectionType"]:checked')).map(cb => cb.value);
                if (inspectionTypes.length === 0) {
                    Swal.fire('เกิดข้อผิดพลาด', 'กรุณาเลือก "ต้องการตรวจพิสูจน์" อย่างน้อย 1 รายการ', 'error');
                    return;
                }

                // 4. ตรวจสอบวันที่ซ้ำกัน
                const date1 = document.getElementById('date1')._flatpickr.input.value;
                const date2 = document.getElementById('date2')._flatpickr.input.value;
                const date3 = document.getElementById('date3')._flatpickr.input.value;
                
                if (!date1 || !date2 || !date3) {
                        Swal.fire('เกิดข้อผิดพลาด', 'กรุณาเลือกวันที่นัดหมายให้ครบทั้ง 3 อันดับ', 'error');
                        return;
                }

                if (date1 === date2 || date1 === date3 || date2 === date3) {
                    Swal.fire('วันที่ซ้ำกัน', 'ท่านได้ขอตรวจพิสูจน์วันนี้แล้ว กรุณาเปลี่ยนวัน', 'error');
                    return;
                }
                
                // 5. (Requirement 3) ตรวจสอบว่าแนบไฟล์อย่างน้อย 1 ไฟล์ (ถูกปิดการใช้งาน)
                /*
                if (fileUploadInput.files.length === 0) {
                    Swal.fire('เกิดข้อผิดพลาด', 'กรุณาแนบรูปหนังสือนำส่งและเอกสารที่เกี่ยวข้อง', 'error');
                    return;
                }
                */

                // --- (Requirement 4) สร้าง Preview ก่อนส่ง ---
                
                // 1. รวบรวมข้อมูลสำหรับ Preview
                const formData = new FormData(form);
                const data = Object.fromEntries(formData.entries());
                
                // 2. จัดการข้อมูลชนิดรถ
                let carTypeDisplay = data.carType;
                if (data.carType === 'อื่น ๆ') {
                    carTypeDisplay = data.carTypeOther;
                }

                // 3. จัดการวันที่ (ใช้ altInput.value ที่เป็น พ.ศ. แล้ว)
                const date1Display = document.getElementById('date1')._flatpickr.altInput.value;
                const date2Display = document.getElementById('date2')._flatpickr.altInput.value;
                const date3Display = document.getElementById('date3')._flatpickr.altInput.value;
                
                // 4. จัดการไฟล์
                const files = Array.from(fileUploadInput.files);
                let fileListHtml = '<li>ไม่มีไฟล์แนบ</li>';
                if (files.length > 0) {
                    fileListHtml = files.map(f => `<li>${f.name}</li>`).join('');
                }

                // 5. สร้าง HTML สำหรับ SweetAlert
                const previewHtml = `
                    <div class="text-left text-sm space-y-2">
                        <p><strong>ชื่อ-สกุล:</strong> ${data.firstName} ${data.lastName}</p>
                        <p><strong>เบอร์โทร:</strong> ${data.phone}</p>
                        <p><strong>สถานะ:</strong> ${data.status}</p>
                        <hr>
                        <p><strong>ชนิดรถ:</strong> ${carTypeDisplay}</p>
                        <p><strong>สี:</strong> ${data.carColor}</p>
                        <p><strong>ยี่ห้อ:</strong> ${data.carMake}</p>
                        <p><strong>รุ่น:</strong> ${data.carModel}</p>
                        <p><strong>ทะเบียน:</strong> ${data.licensePlate} ${data.province}</p>
                        <hr>
                        <p><strong>ต้องการตรวจ:</strong></p>
                        <ul class="list-disc list-inside ml-4">${inspectionTypes.map(item => `<li>${item}</li>`).join('')}</ul>
                        <hr>
                        <p><strong>วันที่นัดหมาย:</strong></p>
                        <ul class="list-disc list-inside ml-4">
                            <li><strong>อันดับ 1:</strong> ${date1Display}</li>
                            <li><strong>อันดับ 2:</strong> ${date2Display}</li>
                            <li><strong>อันดับ 3:</strong> ${date3Display}</li>
                        </ul>
                        <hr>
                        <p><strong>ไฟล์ที่แนบ:</strong></p>
                        <ul class="list-disc list-inside ml-4">${fileListHtml}</ul>
                    </div>
                `;

                // 6. แสดง SweetAlert
                Swal.fire({
                    title: 'โปรดตรวจสอบข้อมูล',
                    html: previewHtml,
                    icon: 'info',
                    showCancelButton: true,
                    confirmButtonColor: '#7F141F',
                    cancelButtonColor: '#6c757d',
                    confirmButtonText: 'ยืนยันการส่งข้อมูล',
                    cancelButtonText: 'แก้ไข',
                    width: '80%'
                }).then(async (result) => {
                    // 7. ถ้ากดยืนยัน (Confirm)
                    if (result.isConfirmed) {
                        
                        // --- (ย้ายโค้ดเดิมมาไว้ตรงนี้) ---
                        // --- เริ่มกระบวนการส่งข้อมูล ---
                        const submitButton = document.getElementById('submitButton');
                        submitButton.disabled = true;
                        submitButton.textContent = 'กำลังบันทึกข้อมูล...';

                        Swal.fire({
                            title: 'กำลังบันทึกข้อมูล',
                            text: 'กรุณารอสักครู่...',
                            allowOutsideClick: false,
                            didOpen: () => {
                                Swal.showLoading();
                            }
                        });

                        // 5.5) & 8. แปลงไฟล์เป็น Base64
                        const filePromises = Array.from(fileUploadInput.files).map(readFileAsBase64);
                        let filesBase64;
                        try {
                            filesBase64 = await Promise.all(filePromises);
                        } catch (error) {
                            console.error('File Read Error:', error);
                            Swal.fire('เกิดข้อผิดพลาด', 'ไม่สามารถอ่านไฟล์ที่แนบได้', 'error');
                            submitButton.disabled = false;
                            submitButton.textContent = 'ยืนยันการนัดหมาย';
                            return;
                        }

                        // รวบรวมข้อมูลจาก Form (เรามี data, inspectionTypes, filesBase64, liffUserId แล้ว)
                        const dataToSend = Object.fromEntries(new FormData(form).entries());

                        // เพิ่มข้อมูลที่ไม่ได้อยู่ใน Form
                        dataToSend.liffUserId = liffUserId;
                        dataToSend.inspectionTypes = inspectionTypes; // ส่งเป็น array
                        dataToSend.files = filesBase64; // ส่ง array ของ object {filename, mimeType, base64String}
                        
                        // แก้ไขข้อมูลชนิดรถ ถ้าเลือก "อื่น ๆ"
                        if (dataToSend.carType === 'อื่น ๆ') {
                            dataToSend.carType = dataToSend.carTypeOther;
                        }
                        delete dataToSend.carTypeOther; // ลบ field ที่ไม่จำเป็น
                        
                        // ส่งข้อมูลไปยัง Google Apps Script
                        try {
                            const response = await fetch(GAS_WEB_APP_URL, {
                                method: 'POST',
                                body: JSON.stringify(dataToSend),
                                headers: {
                                    'Content-Type': 'text/plain;charset=utf-8', 
                                },
                            });

                            const result = await response.json();

                            if (result.status === 'success') {
                                // 6. บันทึกข้อมูลสำเร็จ
                                Swal.fire({
                                    icon: 'success',
                                    title: 'บันทึกข้อมูลสำเร็จ',
                                    text: 'การนัดหมายของท่านถูกส่งเรียบร้อยแล้ว',
                                }).then(() => {
                                    form.reset(); // ล้างฟอร์ม
                                    fileListDiv.innerHTML = ''; // ล้างรายการไฟล์
                                    if (liff.isInClient()) {
                                        liff.closeWindow();
                                    }
                                });
                            } else {
                                // 6. บันทึกข้อมูลไม่สำเร็จ
                                throw new Error(result.message || 'Unknown error');
                            }

                        } catch (error) {
                            console.error('GAS Fetch Error:', error);
                            Swal.fire('บันทึกข้อมูลไม่สำเร็จ', `เกิดข้อผิดพลาดในการเชื่อมต่อ: ${error.message}`, 'error');
                        } finally {
                            submitButton.disabled = false;
                            submitButton.textContent = 'ยืนยันการนัดหมาย';
                        }
                        // --- (สิ้นสุดโค้ดเดิม) ---

                    } else {
                        // 8. ถ้ากด "แก้ไข" (Cancel)
                        // ไม่ต้องทำอะไร SweetAlert จะปิดไปเอง
                    }
                });
            });
        });

    </script>
</body>
</html>
