<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026 스마트 학사 캘린더</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@400;600;800&display=swap');
        body { font-family: 'Pretendard', sans-serif; }
        .calendar-grid { display: grid; grid-template-columns: repeat(7, 1fr); }
        .day-cell { min-height: 100px; border: 0.5px solid #f1f5f9; }
        .event-dot { width: 6px; height: 6px; border-radius: 50%; display: inline-block; margin-right: 2px; }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 min-h-screen">

    <nav class="bg-white border-b sticky top-0 z-20 shadow-sm">
        <div class="max-w-4xl mx-auto px-4 py-4 flex justify-between items-center">
            <h1 class="text-xl font-extrabold text-blue-600 tracking-tight">📅 2026 학사일정</h1>
            <div class="flex bg-slate-100 p-1 rounded-xl">
                <button id="viewListBtn" onclick="switchView('list')" class="px-4 py-1.5 rounded-lg text-sm font-bold transition-all bg-white shadow-sm text-blue-600">리스트형</button>
                <button id="viewCalBtn" onclick="switchView('cal')" class="px-4 py-1.5 rounded-lg text-sm font-bold transition-all text-slate-500">달력형</button>
            </div>
        </div>
    </nav>

    <main class="max-w-4xl mx-auto px-4 mt-6">
        
        <div id="searchContainer" class="relative mb-6">
            <input type="text" id="searchInput" placeholder="일정 검색 (시험, 수강신청 등)..." 
                class="w-full pl-12 pr-4 py-4 rounded-2xl bg-white border-none shadow-md focus:ring-2 focus:ring-blue-500 outline-none text-lg">
            <i class="fa-solid fa-search absolute left-5 top-5 text-slate-300"></i>
        </div>

        <div id="listView" class="space-y-3 pb-10"></div>

        <div id="calView" class="hidden pb-10">
            <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-slate-100">
                <div class="flex justify-between items-center p-6 border-b">
                    <button onclick="changeMonth(-1)" class="p-2 hover:bg-slate-100 rounded-full transition-colors"><i class="fa-solid fa-chevron-left"></i></button>
                    <h2 id="currentMonthYear" class="text-xl font-bold text-slate-800">2026년 3월</h2>
                    <button onclick="changeMonth(1)" class="p-2 hover:bg-slate-100 rounded-full transition-colors"><i class="fa-solid fa-chevron-right"></i></button>
                </div>
                <div class="calendar-grid bg-slate-50 text-center font-bold text-xs text-slate-400 py-3 border-b">
                    <div class="text-red-500 uppercase">Sun</div><div class="uppercase">Mon</div><div class="uppercase">Tue</div><div class="uppercase">Wed</div><div class="uppercase">Thu</div><div class="uppercase">Fri</div><div class="text-blue-500 uppercase">Sat</div>
                </div>
                <div id="calendarDays" class="calendar-grid bg-white">
                    </div>
            </div>
            <div id="dayDetail" class="mt-6 p-6 bg-blue-50 rounded-2xl hidden">
                <h4 id="detailDate" class="font-bold text-blue-800 mb-3 underline decoration-blue-200">일정 상세</h4>
                <div id="detailContent" class="space-y-2"></div>
            </div>
        </div>
    </main>

    <script>
        // 전체 데이터 (요청하신 대로 이미지 전체 데이터 반영)
         const rawData = [
            // 1학기 일정 (이미지 2)
            { s: "2025-12-29", e: "2026-01-14", t: "정시모집 원서접수", c: "입시" },
            { s: "2026-01-05", e: "2026-02-13", t: "복학 신청기간", c: "학사" },
            { s: "2026-01-05", e: "2026-01-07", t: "학생 성적확인 및 이의 신청기간", c: "성적" },
            { s: "2026-01-19", e: "2026-01-23", t: "2026-1학기 전과·재입학 신청기간", c: "학사" },
            { s: "2026-01-22", e: "", t: "진급 및 졸업사정회", c: "학사" },
            { s: "2026-02-03", e: "2026-02-05", t: "신입생 등록기간(수시, 정시 합격자)", c: "입시" },
            { s: "2026-02-05", e: "", t: "전기 학위수여식 (졸업식)", c: "행사" },
            { s: "2026-02-09", e: "2026-02-13", t: "2026-1학기 수강신청 기간", c: "수강" },
            { s: "2026-02-23", e: "2026-02-27", t: "2026-1학기 등록금 납부 기간", c: "학사" },
            { s: "2026-02-26", e: "", t: "2026학년도 입학식 오리엔테이션", c: "행사" },
            { s: "2026-03-03", e: "", t: "1학기 개강 (입학식)", c: "학사" },
            { s: "2026-03-03", e: "2026-03-09", t: "수강신청 정정기간", c: "수강" },
            { s: "2026-03-05", e: "", t: "1학기 개강 예배", c: "행사" },
            { s: "2026-03-27", e: "", t: "1학기 수업일수 1/4선", c: "학사" },
            { s: "2026-04-01", e: "", t: "재적생 변동상황보고", c: "학사" },
            { s: "2026-04-09", e: "", t: "부활절 예배주간", c: "행사" },
            { s: "2026-04-14", e: "2026-04-20", t: "1학기 중간고사 평가 권장기간", c: "시험" },
            { s: "2026-04-23", e: "", t: "1학기 수업일수 2/4선", c: "학사" },
            { s: "2026-05-01", e: "", t: "근로자의 날 / 개교기념일 (휴업)", c: "휴일" },
            { s: "2026-05-05", e: "", t: "어린이날 (휴업)", c: "휴일" },
            { s: "2026-05-13", e: "2026-05-14", t: "비전축제 (휴업)", c: "행사" },
            { s: "2026-05-21", e: "", t: "1학기 수업일수 3/4선", c: "학사" },
            { s: "2026-05-25", e: "", t: "석가탄신일 대체휴업일 (휴업)", c: "휴일" },
            { s: "2026-06-03", e: "", t: "지방선거 (휴업)", c: "휴일" },
            { s: "2026-06-09", e: "2026-06-16", t: "보강주, 계절학기 수강신청", c: "학사" },
            { s: "2026-06-11", e: "", t: "1학기 종강 예배", c: "행사" },
            { s: "2026-06-17", e: "2026-06-23", t: "1학기 기말고사 기간", c: "시험" },
            { s: "2026-06-23", e: "", t: "1학기 수업일수 4/4선", c: "학사" },
            { s: "2026-06-24", e: "2026-08-31", t: "하계방학 및 계절학기(현장실습)", c: "학사" },
            { s: "2026-06-29", e: "2026-07-01", t: "학생 성적확인 및 성적 이의 신청기간", c: "성적" },
            { s: "2026-07-06", e: "2026-08-14", t: "복학 신청기간", c: "학사" },
            { s: "2026-07-09", e: "", t: "성적 사정회", c: "성적" },
            { s: "2026-07-20", e: "2026-07-30", t: "전과·재입학 신청기간", c: "학사" },
            { s: "2026-07-23", e: "", t: "진급 및 졸업사정회", c: "학사" },

            // 2학기 일정 (이미지 1)
            { s: "2026-08-03", e: "", t: "후기 학위수여식", c: "행사" },
            { s: "2026-08-14", e: "2026-08-21", t: "2학기 수강신청 기간", c: "수강" },
            { s: "2026-08-24", e: "2026-08-28", t: "2학기 등록금 납부기간", c: "학사" },
            { s: "2026-09-01", e: "", t: "2학기 개강", c: "학사" },
            { s: "2026-09-01", e: "2026-09-07", t: "수강신청 정정기간", c: "수강" },
            { s: "2026-09-03", e: "", t: "2학기 개강예배", c: "행사" },
            { s: "2026-09-07", e: "2026-09-30", t: "수시모집 1차 원서접수", c: "입시" },
            { s: "2026-09-24", e: "2026-09-25", t: "추석 연휴 (휴업)", c: "휴일" },
            { s: "2026-09-29", e: "", t: "2학기 수업일수 1/4선", c: "학사" },
            { s: "2026-10-01", e: "", t: "재적생 변동상황보고", c: "학사" },
            { s: "2026-10-05", e: "", t: "개천절 대체휴일 (휴업)", c: "휴일" },
            { s: "2026-10-09", e: "", t: "한글날 (휴업)", c: "휴일" },
            { s: "2026-10-17", e: "", t: "수시모집 1차 면접", c: "입시" },
            { s: "2026-10-19", e: "2026-10-23", t: "2학기 중간고사 평가 권장기간", c: "시험" },
            { s: "2026-10-22", e: "", t: "비전 EXPO 및 축제", c: "행사" },
            { s: "2026-10-28", e: "", t: "2학기 수업일수 2/4선", c: "학사" },
            { s: "2026-11-11", e: "2026-11-25", t: "수시모집 2차 원서접수", c: "입시" },
            { s: "2026-11-19", e: "", t: "추수 감사 예배", c: "행사" },
            { s: "2026-11-23", e: "", t: "2학기 수업일수 3/4선", c: "학사" },
            { s: "2026-11-26", e: "", t: "학생회장 선거일", c: "행사" },
            { s: "2026-12-05", e: "", t: "수시모집 2차 면접", c: "입시" },
            { s: "2026-12-08", e: "2026-12-11", t: "보강주, 계절학기 수강신청", c: "학사" },
            { s: "2026-12-10", e: "", t: "2학기 종강예배", c: "행사" },
            { s: "2026-12-14", e: "2026-12-18", t: "2학기 기말고사 기간", c: "시험" },
            { s: "2026-12-18", e: "", t: "2학기 수업일수 4/4선", c: "학사" },
            { s: "2026-12-21", e: "2027-02-26", t: "겨울방학 및 동계 계절학기", c: "학사" },
            { s: "2027-01-04", e: "2027-01-20", t: "정시모집 원서접수", c: "입시" },
            { s: "2027-02-04", e: "", t: "전기 학위수여식", c: "행사" }
        ];


        let currentView = 'list';
        let calDate = new Date(2026, 2, 1); // 2026년 3월부터 시작

        function switchView(view) {
            currentView = view;
            const isList = view === 'list';
            document.getElementById('listView').classList.toggle('hidden', !isList);
            document.getElementById('searchContainer').classList.toggle('hidden', !isList);
            document.getElementById('calView').classList.toggle('hidden', isList);
            
            // 버튼 스타일 업데이트
            document.getElementById('viewListBtn').className = isList ? "px-4 py-1.5 rounded-lg text-sm font-bold bg-white shadow-sm text-blue-600" : "px-4 py-1.5 rounded-lg text-sm font-bold text-slate-500";
            document.getElementById('viewCalBtn').className = !isList ? "px-4 py-1.5 rounded-lg text-sm font-bold bg-white shadow-sm text-blue-600" : "px-4 py-1.5 rounded-lg text-sm font-bold text-slate-500";
            
            if(!isList) renderCalendar();
        }

        function changeMonth(diff) {
            calDate.setMonth(calDate.getMonth() + diff);
            renderCalendar();
        }

        function renderCalendar() {
            const year = calDate.getFullYear();
            const month = calDate.getMonth();
            document.getElementById('currentMonthYear').innerText = `${year}년 ${month + 1}월`;
            
            const firstDay = new Date(year, month, 1).getDay();
            const lastDate = new Date(year, month + 1, 0).getDate();
            const calDays = document.getElementById('calendarDays');
            calDays.innerHTML = "";

            // 빈 칸 (이전 달 날짜 공간)
            for (let i = 0; i < firstDay; i++) {
                const div = document.createElement('div');
                div.className = "day-cell bg-slate-50/50";
                calDays.appendChild(div);
            }

            // 날짜 칸 생성
            for (let d = 1; d <= lastDate; d++) {
                const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}`;
                const dayEvents = rawData.filter(item => {
                    const start = item.s;
                    const end = item.e || item.s;
                    return dateStr >= start && dateStr <= end;
                });

                const div = document.createElement('div');
                div.className = `day-cell p-2 border-r border-b cursor-pointer hover:bg-blue-50 transition-colors ${d === new Date().getDate() && month === new Date().getMonth() ? 'bg-yellow-50' : ''}`;
                div.onclick = () => showDayDetail(dateStr, dayEvents);
                
                let dots = dayEvents.map(e => {
                    let color = "bg-blue-400";
                    if(e.c === "시험") color = "bg-red-400";
                    if(e.c === "휴일") color = "bg-orange-400";
                    return `<span class="event-dot ${color}"></span>`;
                }).join('');

                div.innerHTML = `
                    <div class="text-sm font-medium ${new Date(year, month, d).getDay() === 0 ? 'text-red-500' : ''}">${d}</div>
                    <div class="mt-1 flex flex-wrap">${dots}</div>
                `;
                calDays.appendChild(div);
            }
        }

        function showDayDetail(date, events) {
            const detailBox = document.getElementById('dayDetail');
            const content = document.getElementById('detailContent');
            document.getElementById('detailDate').innerText = `${date} 일정 상세`;
            
            if (events.length === 0) {
                content.innerHTML = "<p class='text-slate-400 text-sm'>일정이 없습니다.</p>";
            } else {
                content.innerHTML = events.map(e => `
                    <div class="bg-white p-3 rounded-xl shadow-sm border border-blue-100 flex justify-between items-center">
                        <span class="font-bold text-slate-700">${e.t}</span>
                        <span class="text-[10px] font-bold bg-blue-100 text-blue-600 px-2 py-1 rounded-md uppercase">${e.c}</span>
                    </div>
                `).join('');
            }
            detailBox.classList.remove('hidden');
        }

        // 리스트형 렌더링 (기존 로직 유지)
        function renderList(filter = "") {
            const listContainer = document.getElementById('listView');
            const filtered = rawData.filter(item => item.t.includes(filter));
            listContainer.innerHTML = filtered.map(item => `
                <div class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 flex justify-between items-center hover:shadow-md transition-all">
                    <div>
                        <span class="px-2 py-0.5 rounded-md text-[10px] font-bold bg-slate-100 text-slate-500 uppercase tracking-wider">${item.c}</span>
                        <h3 class="text-lg font-bold text-slate-800 mt-1">${item.t}</h3>
                        <p class="text-slate-400 text-sm mt-1">${item.s} ${item.e ? '~ ' + item.e : ''}</p>
                    </div>
                    <button onclick="window.open('https://www.google.com/calendar/render?action=TEMPLATE&text=${encodeURIComponent(item.t)}&dates=${item.s.replace(/-/g,'')}/${(item.e||item.s).replace(/-/g,'')}', '_blank')" 
                        class="bg-blue-50 text-blue-600 px-4 py-2 rounded-xl text-sm font-bold hover:bg-blue-600 hover:text-white transition-all">추가</button>
                </div>
            `).join('');
        }

        document.getElementById('searchInput').addEventListener('input', (e) => renderList(e.target.value));
        window.onload = () => renderList();
    </script>
</body>
</html>
