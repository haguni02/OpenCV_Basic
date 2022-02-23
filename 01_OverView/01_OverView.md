# OpenCV 기초

### 컴퓨터 비전 개요
* 컴퓨터 비전 : 컴퓨터를 이용하여 이미지 또는 동영상으로부터 의미 있는 정보를 추출하는 방법을 연구하는 학문
* 영상 처리 : 컴퓨터 비전을 좀 더 용이하게 하기 위해서  영상 화질 개선등의 처리를 하는 학문 
* 컴퓨터 비전 사전 지식 : 행렬, 미분, C++ 기본 문법
* 픽셀(pixel = element = 화소) : 영상을 구성하는 최소 단위
* 영상좌표계 : 2차원 xy 좌표계 0 ~ w-1(x좌표), 0 ~ h-1(y좌표)
* 영상좌표계 (w x h 크기의 영상) -> 2차원 행렬로 표현 가능 (M x N 행렬)
* 그레이 스케일 영상 : 1채널 0~255 사이의 정수값 (c/c++ : unsigned char)
* 트루 컬러 영상 : R,G,B 3채널 각 채널은 0~255 사이의 정수값
* 컴퓨터 영상 파일 형식 : BMP (압축x), JPG(손실압축), GIF(무손실압축), PNG (손실압축, 알파채널=투명도 포함)

### OpenCV 개요
* 오픈소스로 개발되고 있는 컴퓨터 비전 및 머신 러닝 라이브러리 
* 2500개가 넘는 최신 컴퓨터 비전 알고리즘과 머신 러닝 알고리즘을 포함
* 실시간 처리를 고려하여 만들어졌기 때문에 다양한 하드웨어 플랫폼에서 매우 빠르게 동작 
* 기본적으로 C/C++ 언어로 작성되어 있지만 Python, Java, Matlab, JavaScript 등의 인터페이스도 제공 
* Windows, Linux, MacOS 등 운영 체제를 지원, 안드로이드와 iOS 같은 모바일 환경도 지원 
* OpenCV 기능은 대부분 병렬 처리로 동작 (MMX, SSE, AVX, NEON 등 CPU 특화 명령어도 지원 : CUDA, OpenCL을 통한 GPU 활용 지원)
* BSD 라이선스를 따르고 있어 연구용이나 상업적인 용도로 자유롭게 사용 가능 

### OpenCV 주요 모듈
* <img src="./img/OCV001.PNG" width="600"/>
* OpenCV 모듈은 각각 별도의 *.lib 파일과  *.dll 파일로 만들어 짐 (예를 들어 OpenCV 4.0.0 버전인 경우 core 모듈은 opencv_core400.lib 파일과 opencv_core400.dll 파일이 존재)
* <img src="./img/OCV002.PNG" width="600"/>

### OpenCV 관련 사이트
* [OpenCV 공식 사이트](https://opencv.org/)
* [OpenCV 문서 사이트](https://docs.opencv.org/4.0.0/)
* [OpenCV 질문/답변 사이트](https://answers.opencv.org/)
* [OpenCV 최신 소스 코드 저장소](https://github.com/opencv/opencv/)
* [OpenCV 추가 모듈 소스 저장소](https://github.com/opencv/opencv_contrib/)

### OpenCV 설치하기
* Windows에서 OpenCV 설치 하는 법 
> 1) [OpenCV 설치 사이트](https://opencv.org/releases.html)에서 설치 실행 파일을 직접 내려받아 설치하는 방법
> 2) OpenCV 소스 코드를 내려받은 후 직접 빌드하여 설치하는 방법 
* OpenCV 설치 실행 파일 이용해 설치하기 
> 1) OpenCV Releases 사이트에서 설치 실행 파일 다운로드
> 2) 설치 폴더 지정<br/><img src="./img/OCV003.PNG" />
> 3) 설치 폴더 구조<br/><img src="./img/OCV004.PNG" />
> * C:\opencv\build\x64\vc15\ 
> > * visual studion 2017 버전으로 빌드된 라이브러리 파일이 있는 폴더 사용
> > * bin 폴더에는 OpenCV 프로그램 실행 시 필요한 동적 연결 라이브러리 파일과 OpenCV 유틸리티 프로그램 생성 
> > * lib 폴더에는 DLL 파일이 만들어질 때 함께 생성되는 import library 
> > * 동적 연결 라이브러리 파일 이름은 opencv_world400.dll, opencv_world400d.dll(~d가 붙으면 디버그 모드에서 사용)
> 5) OpenCV 응용 프로그램을 실행할 떄 OpenCV DLL 파일이 필요하므로 OpenCV DLL 파일이 있는 폴더를 시스템 환경 변수 PATH에 추가 <br/> <img src="./img/OCV005.PNG" />
> 6) OpenCV 버전 확인 <br/> <img src="./img/OCV006.PNG" />
* OpenCV 추가 모듈을 사용하거나 자신의 컴퓨터 시스템에 최적화된 OpenCV DLL 파일을 사용하려면 OpenCV 소스 코드를 직접 빌드하여 OpenCV 라이브러리 설치 

### Visual Studio에서 OpenCV 라이브러리 설정
1) Visual Studio 프로젝트 속성에서 OpenCV 관련 설정 <br/> <img src="./img/OCV007.PNG" />
2) <img src="./img/OCV008.PNG" />
3) <img src="./img/OCV009.PNG" />
4) <img src="./img/OCV010.PNG" />

