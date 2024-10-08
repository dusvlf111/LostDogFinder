# LostDogFinder

유기견 찾기 프로그램(LostDogFinder)은 여러 유기견 보호소 사이트에서 데이터를 크롤링하고, 사용자가 제공한 개의 사진과 유기견 사진의 유사도를 비교하여 유기견을 찾는 데 도움을 주는 자바 기반 애플리케이션입니다.

## 프로젝트 개요

- **주요 기능**:
  - 여러 유기견 보호소 웹사이트에서 데이터를 크롤링
  - 사용자가 제공한 개의 사진과 유기견 사진의 유사도를 분석
  - 유사도가 높은 유기견 정보를 사용자에게 제공

- **기술 스택**:
  - **언어**: Java
  - **크롤링**: Jsoup
  - **이미지 처리**: OpenCV, Apache Commons Imaging
  - **멀티쓰레딩**: Java `ExecutorService`
  - **데이터베이스**: H2 Database
  - **로그**: Log4j2

## 설치 및 실행

### 요구 사항

- Java 11 이상
- Maven 3.6 이상

### 설치 방법

1. 저장소를 클론합니다:

    ```bash
    git clone https://github.com/yourusername/LostDogFinder.git
    ```

2. 프로젝트 디렉터리로 이동합니다:

    ```bash
    cd LostDogFinder
    ```

3. 필요한 의존성을 설치하고 프로젝트를 빌드합니다:

    ```bash
    mvn clean install
    ```

4. 프로그램을 실행합니다:

    ```bash
    mvn exec:java -Dexec.mainClass="com.lostdogfinder.App"
    ```

## 사용 방법

1. 프로그램을 실행하면 유기견 보호소 사이트에서 데이터를 자동으로 크롤링합니다.
2. 사용자 인터페이스를 통해 자신의 개 사진을 업로드합니다.
3. 프로그램이 업로드된 사진과 유기견 사진들을 비교하여 유사도가 높은 유기견 리스트를 제공합니다.
4. 결과는 사용자 인터페이스에서 확인할 수 있으며, 유기견의 이름, 사진, 위치 등의 정보가 표시됩니다.

## 파일 구조

프로젝트의 주요 디렉터리 및 파일 구조는 다음과 같습니다:

```
/LostDogFinder
│
├── /src
│   ├── /main
│   │   ├── /java
│   │   │   ├── /com/lostdogfinder
│   │   │   │   ├── App.java                  // 메인 애플리케이션 클래스
│   │   │   │   ├── /crawler                  // 크롤링 관련 클래스
│   │   │   │   ├── /database                 // 데이터베이스 관리 클래스
│   │   │   │   ├── /image                    // 이미지 처리 및 유사도 분석 클래스
│   │   │   │   ├── /ui                       // 사용자 인터페이스 관련 클래스
│   │   │   │   └── /utils                    // 유틸리티 클래스
│   ├── /resources
│   │   ├── application.properties            // 애플리케이션 설정 파일
│   │   └── log4j2.xml                        // 로깅 설정 파일
├── /lib                                      // 외부 라이브러리
├── /bin                                      // 컴파일된 클래스 파일
└── /logs                                     // 로그 파일
```

## 기여

기여를 환영합니다! 이 프로젝트에 기여하려면 다음 단계를 따르세요:

1. 이 저장소를 포크하세요.
2. 기능 브랜치를 생성하세요: `git checkout -b feature/기능명`.
3. 변경 사항을 커밋하세요: `git commit -m 'Add 새로운 기능'`.
4. 브랜치로 푸시하세요: `git push origin feature/기능명`.
5. Pull Request를 생성하세요.

## 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 문의

프로젝트 관련 문의 사항이 있으시면 마음속으로 생각해주세요


