###RCA_hyang
https://www.visualsvn.com/downloads/
### NRPMS
	+ D:\source\RPMS
	+ RPMS UI 구성 및 데이터 처리.pptx 참고
	+ RPMS UI 개발 진행률 (참고)
	+ view는 달라도 접근하는 store는 하나
	+ setting sync 다운 (환경세팅 백업 )
### 개발가이드 툴 (개발가이드.md)
	+ IDE : VSCode https://code.visualstudio.com/Download
	+ plug-in :  
		- VSCode 를 실행 
		-왼쪽에 블럭모양 아이콘 (위에서 4번째) 클릭 
		- Eclips Keymap 검색  설치
		- SVN 검색 설치
	+ svn 연결 방법 
		- VSCode 를 실행 
		- 왼쪽에 S모양 아이콘 클릭 
		- Repositories 에서  + 클릭 
		- 주소창에 svn://192.168.0.2/RPMS 입력
		- 주의, 사무실 77777 네트워크 연결시에만 연결이됨.
		- ! 외부에서 연결하고 싶을 시 svn://183.107.19.138/RPMS !
		
### NRPMS 화면구성
	1. view.html
	2. view.js
	3. view.css

#### 화면 로딩 로직
	1. view.html
	2. view.js
	3. utils
	
### Promise
	+ 자바스크립트 비동기 처리에 사용되는 객체 -> 비동기 처리: 특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 자바스크립트의 특성
	https://joshua1988.github.io/web-development/javascript/promise-for-beginners/

#### 라이브러리 사용방법
	1. git에서 코드 copy
	2. D:\source\RPMS\assets\lib\dataTables\js 에 라이브러리 js 코드 추가
	3. 라이브러리에서 사용한 css file copy 후 추가
	3. config.js -> require.config({ 'colResize': '../lib/dataTables/js/ColReorderWithResize' })

#### table resize 라이브러리
	https://github.com/jeffreydwalter/ColReorderWithResize
	ColReorderWithResize.js
	
#### 멀티 셀렉터 (multi-selector)
	+ https://developer.snapappointments.com/bootstrap-select/
	+ base.js -> makeMultipleSelect()
	
#### html 이미지 저장 (screenshot, capture 캡처)
	+ https://html2canvas.hertzen.com/
	+ base.js -> screenshot()
	+ [ html2canvas(el.get(0), {
				backgroundColor: "white",   /*배경 색 선택. 기본값 : 흰색, 투명으로 하려면(transparent)*/
				width: container.width() + 200,
				height: container.height() + 300
			}) ]
	html에 <div class="container screenshot"> -> screenshot에 해당하는 html만 캡처
	
### 파일 업로드 (fileinput)
	+ https://plugins.krajee.com/file-input
	+ https://github.com/kartik-v/bootstrap-fileinput
	+ base.js -> fileinput()
	+ html에 input type="file"
	
### 권한 설정 (grant)
	+ base -> applyRoles() -> utils -> hasGrant
	+ html 앞에 data-roles="" or data-except-roles 추가
	
### tab화면
	+ base.js -> makeViewTab()
	+ [ <div class="tab-pane fade ${index == 0 ? 'show active' : ''}" id="TAB_NRPMS_${vNameFull}"  	role="tabpanel" aria-labelledby="LINK_NRPMS_${vNameFull}">` ]
	+  NRPMS_viewName_tab
	
### summernote (에디터 editor [편집기])
	+ https://summernote.org/getting-started/
	+ base.js -> makeSummernote()
	
### chart c3
	+ NRPMS_005 참고
	
	1. loadChartData()
	2. view.chart.load
	3. loadChart()
	
### onTest
	+ view.loadAndShow > utils.loadView > new View > cView.onLoad > cView.onPrepare > cView.onAutoTest (base.js 참고)
	
### toLowerCase
	+ 문자열을 소문자로 변환하여 반환
	+ utils.js [ viewName = viewName.toLowerCase(); ]
	+ toLowerCase() <-> toUpperCase()

### split, trim
	+ split(',') : , 를 기준으로 문자열을 분할
	+ trim : 문자열 좌우에서 공백 제거 [ item.trim() ]

### @media 모바일 환경 고려
	+ bootstrap.custom.css
	+ [ @media (max-width: 768px) {
			#container-depth1,
			#container-depth2 {
			width: 100% !important;
			}
		} ]
		
### 