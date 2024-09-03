### 프로젝트 파일 구조

```
/LostDogFinder
│
├── /src
│   ├── /main
│   │   ├── /java
│   │   │   ├── /com
│   │   │   │   ├── /lostdogfinder
│   │   │   │   │   ├── App.java
│   │   │   │   │   ├── /crawler
│   │   │   │   │   │   ├── SiteManager.java
│   │   │   │   │   │   ├── SiteCrawler.java
│   │   │   │   │   │   ├── CrawlerTask.java
│   │   │   │   │   │   └── CrawlerException.java
│   │   │   │   │   ├── /database
│   │   │   │   │   │   ├── DatabaseManager.java
│   │   │   │   │   │   └── DogInfo.java
│   │   │   │   │   ├── /image
│   │   │   │   │   │   ├── ImageProcessor.java
│   │   │   │   │   │   ├── ImageLoader.java
│   │   │   │   │   │   ├── ImageComparator.java
│   │   │   │   │   │   ├── ImageComparisonTask.java
│   │   │   │   │   │   └── ImageException.java
│   │   │   │   │   ├── /ui
│   │   │   │   │   │   ├── ResultDisplay.java
│   │   │   │   │   │   └── UIRenderer.java
│   │   │   │   │   └── /utils
│   │   │   │   │       ├── Logger.java
│   │   │   │   │       └── Config.java
│   │   │   │   └── /test
│   │   │   │       ├── CrawlerTest.java
│   │   │   │       ├── ImageProcessorTest.java
│   │   │   │       └── DatabaseTest.java
│   ├── /resources
│   │   ├── application.properties
│   │   └── log4j2.xml
├── /lib
├── /bin
└── /logs
```

### 파일 및 디렉터리 설명

1. **/LostDogFinder**: 프로젝트의 최상위 디렉터리입니다.

2. **/src/main/java/com/lostdogfinder**: 자바 소스 코드가 위치하는 기본 패키지입니다.

    - **App.java**: 애플리케이션의 진입점 클래스. 메인 메서드를 포함하며, 전체 애플리케이션의 흐름을 제어합니다.
    
    - **/crawler**: 크롤링 관련 클래스들이 모여 있는 패키지입니다.
        - **SiteManager.java**: 크롤링을 시작하고 관리하는 클래스.
        - **SiteCrawler.java**: 특정 사이트에서 데이터를 크롤링하는 기능을 가진 클래스.
        - **CrawlerTask.java**: 개별 크롤링 작업을 정의하는 클래스. 멀티쓰레딩을 통해 병렬로 실행됩니다.
        - **CrawlerException.java**: 크롤링 중 발생할 수 있는 예외를 처리하는 클래스.
    
    - **/database**: 데이터베이스 관리 관련 클래스들이 모여 있는 패키지입니다.
        - **DatabaseManager.java**: 데이터베이스 연결 및 쿼리 실행을 관리하는 클래스.
        - **DogInfo.java**: 유기견 정보를 담는 데이터 모델 클래스.
    
    - **/image**: 이미지 처리 및 유사도 분석 관련 클래스들이 모여 있는 패키지입니다.
        - **ImageProcessor.java**: 전체 이미지 처리 과정을 관리하는 클래스.
        - **ImageLoader.java**: 이미지 파일을 로드하는 기능을 가진 클래스.
        - **ImageComparator.java**: 두 이미지 간의 유사도를 비교하는 클래스.
        - **ImageComparisonTask.java**: 멀티쓰레딩을 활용한 이미지 유사도 비교 작업을 정의하는 클래스.
        - **ImageException.java**: 이미지 처리 중 발생할 수 있는 예외를 처리하는 클래스.
    
    - **/ui**: 사용자 인터페이스 관련 클래스들이 모여 있는 패키지입니다.
        - **ResultDisplay.java**: 유사도 분석 결과를 화면에 표시하는 클래스.
        - **UIRenderer.java**: UI 렌더링과 관련된 기능을 담당하는 클래스.
    
    - **/utils**: 공통으로 사용되는 유틸리티 클래스들이 모여 있는 패키지입니다.
        - **Logger.java**: 로깅 기능을 제공하는 클래스.
        - **Config.java**: 설정 파일을 읽고 애플리케이션 설정을 관리하는 클래스.
    
    - **/test**: 테스트 관련 클래스들이 모여 있는 패키지입니다.
        - **CrawlerTest.java**: 크롤러 기능을 테스트하는 클래스.
        - **ImageProcessorTest.java**: 이미지 처리 기능을 테스트하는 클래스.
        - **DatabaseTest.java**: 데이터베이스 관리 기능을 테스트하는 클래스.

3. **/resources**: 리소스 파일이 위치하는 디렉터리입니다.
    - **application.properties**: 애플리케이션 설정 파일.
    - **log4j2.xml**: 로깅 설정 파일.

4. **/lib**: 외부 라이브러리나 JAR 파일을 포함하는 디렉터리입니다.

5. **/bin**: 컴파일된 클래스 파일이 위치하는 디렉터리입니다.

6. **/logs**: 애플리케이션 실행 중 생성되는 로그 파일이 저장되는 디렉터리입니다.

### 설계 요약

- **모듈화**: 크롤링, 데이터베이스 관리, 이미지 처리, UI 등 기능별로 패키지를 나누어 모듈화했습니다. 각 기능은 서로 독립적으로 개발 및 테스트될 수 있습니다.
- **확장성**: 각 기능이 독립적이므로 새로운 기능 추가나 기존 기능 확장이 용이합니다.
- **유지보수성**: 구조가 명확하게 나뉘어 있어 유지보수 시 특정 기능이나 모듈에 집중할 수 있습니다.
- **멀티쓰레딩 사용**: 크롤링과 이미지 비교 작업에서 멀티쓰레딩을 사용하여 병렬 처리를 효율적으로 구현할 수 있습니다.

