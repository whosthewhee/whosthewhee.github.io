GitHub 블로그를 만들기 위해, 먼저 [GitHub 홈페이지](https://github.com/)에 접속해 계정을 만들어주세요. 이미 GitHub 계정이 있으시다면, 준비는 모두 완료되었습니다!

이제 GitHub의 다양한 기능을 활용해, **Jekyll 테마**를 이용한 블로그 제작 과정을 시작해보겠습니다. 이 글에서는 GitHub 가입이 완료된 상태를 전제로, **간단하면서도 강력한 블로그**를 만드는 방법을 하나씩 공유해드릴게요.

## Step1. 테마 선택하기
저는 다양한 Jekyll 테마를 제공하는 여러 사이트를 살펴봤고, 최종적으로 **Chirpy** 테마를 선택하게 되었습니다. 제가 탐색했던 사이트들과 Chirpy 테마를 선택한 이유에 대해 공유하려고 합니다.

**Jekyll 테마 제공 사이트**
-   **[GitHub Jekyll Themes](https://github.com/topics/jekyll-theme)**
GitHub에서 제공하는 Jekyll 테마 모음입니다. 오픈 소스 프로젝트들이 많아, 각 테마의 코드와 업데이트 상황을 쉽게 확인할 수 있습니다.
    
-   **[Jekyll Themes](http://jekyllthemes.org/)** 
다양한 테마를 한눈에 볼 수 있고, 사용하기도 간편합니다. 테마를 별점 순으로 정렬할 수 있는 기능이 있어, 인기 있는 테마를 쉽게 찾아볼 수 있습니다.
    
-   **[Jekyll Themes.io](https://jekyllthemes.io/free)** 
무료 Jekyll 테마를 모아놓은 사이트입니다. 예쁘고 심플한 디자인의 테마가 많이 있어서 블로그 초보자에게도 적합해 보입니다.
    
-   **[Jekyll RC Themes](http://themes.jekyllrc.org/)**
최신 테마들을 만나볼 수 있는 곳입니다. 다양한 카테고리로 테마를 분류해 두어, 원하는 스타일의 테마를 쉽게 찾을 수 있습니다.

저는 Jekyll **Chirpy** 테마를 선택했습니다.

-   **모던하고 깔끔한 디자인**으로 블로그 글에 집중할 수 있습니다.
-   **모바일 최적화**를 지원해 다양한 기기에서 잘 보입니다.
-   **SEO 최적화**, 소셜 미디어 통합 등의 기능을 기본 제공하여, 추가 설정 없이 바로 사용 가능합니다.
-   **커스터마이징이 쉬워** 블로그에 맞게 개성 있게 꾸밀 수 있습니다.

![image](https://github.com/user-attachments/assets/49a31b41-94c7-4b4d-a743-69bc6a0aedd2)


## Step2. 테마 가져오기
가져오는 방법에는 두가지가 있는데

1.  Chirpy 저장소의  [Release](https://github.com/cotes2020/jekyll-theme-chirpy/releases)에서 소스 다운로드
2.  Chirpy 저장소를  [Fork](https://github.com/cotes2020/jekyll-theme-chirpy/fork) 하기 

이 중 하나의 방법을 선택하여 진행하시기 바랍니다.

저는 **Fork**하여 가져오는 방법을 사용해보겠습니다.

먼저 고른 테마 우측 상단의 Fork 버튼을 클릭합니다.

![image](https://github.com/user-attachments/assets/bd1b8cf1-4d34-46c8-9a5e-9c99b46f160b)

Create Fork 버튼을 눌러 내 Repository로 가져옵니다.

![image](https://github.com/user-attachments/assets/e8817df6-c10f-469b-97a3-2eb6a5871eb9)

## Step3. Repository 이름 바꾸기
내 Repository로 와서 상단 Settings탭을 눌러 들어갑니다.
![image](https://github.com/user-attachments/assets/f7c72237-76e1-47ab-a8f7-765b55b76c19)

**General > Repository name** 부분을 [GitHub아이디].github.io로 변경해주세요.
![image](https://github.com/user-attachments/assets/d74f4ef6-d5ef-4c6d-90b8-e22b9d053797)


## Step4. Local로 소스코드 가져오기

> 사족) Jekyll 테마로 블로그를 만드는 여러 방법을 봤는데, 어떤 사람들은 Local로 소스를 가져오지 않고도 GitHub에서 `_config.yml` 코드만 수정해도 블로그가 바로 나타나더라고요. 하지만 Chirpy 테마는 그런 방법으로는 안 되는 것 같아요(아마도). 결국 Local로 소스를 받아서 Ruby와 Jekyll을 설치하고 나서야 예쁜 블로그를 볼 수 있었습니다. (해보다가 시간 낭비한 사람, 바로 나...)
>
> 아무튼 이제 반 정도 왔으니, 다시 힘내서 블로그를 만들어봅시다!

git clone을 이용해서 local로 소스코드를 복사해옵니다.
```bash
❯ git clone https://github.com/whosthewhee/whosthewhee.github.io.git
```

![image](https://github.com/user-attachments/assets/f86334f1-0855-4a64-8ad3-2c6f3a56ffc5)

## Step5. Local에서 실행하기

*저는 WSL 환경에서 진행했습니다.
Ubuntu 버전 : 22.04.3*

먼저 jekyll 실행을 위해 필요한 모듈을 설치합니다.
1. HomeBrew로 ruby 설치
```bash
❯ brew install ruby
```
2. Ruby가 설치된 후, Jekyll을 설치합니다.
```bash 
❯ gem install jekyll bundler
```

3. 환경 변수 설정
Ruby Gems가 올바르게 설치되고 인식되도록 환경 변수를 설정해야 합니다. .zshrc 또는 .bashrc 파일에 다음 줄을 추가하세요
```bash 
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc source ~/.zshrc
```

4. Jekyll 실행
```bash 
jekyll serve
```
정상적으로 수행됐다면 아래와 같이 출력됩니다.
![image](https://github.com/user-attachments/assets/851909be-8b68-44a4-a378-80cf52e24637)

 출력 창에 나타난 Server address: http://127.0.0.1:4000/
브라우저를 열어서 해당 주소를 입력해 보면, 아래와 같이 기본 블로그 화면이 나타납니다.

![image](https://github.com/user-attachments/assets/e63a6db3-a80f-4a51-bb20-6664a3be4abf)

이제 기본적인 설정을 적용해보겠습니다.

### _config.yml 수정
lang: ko-KR
timezone: Asia/Seoul
url: "https://whosthewhee.github.io"

_config.yml을 수정하면 jekyll을 재구동 해줘야 변경사항이 적용됩니다.