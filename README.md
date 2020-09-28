# google image crawling





> #### 참고 git book
>
> https://beomi.github.io/gb-crawling/
>
> https://j-remind.tistory.com/61
>
> https://ecsimsw.tistory.com/entry/Google-image-crawler-Crawling-Scraping-python



---

#### 설치 항목 



`Selenium` **설치**

```
pip install selenium
```

`BeautifulSoup` **설치**

```
pip install bs4
```

> [ pip란 ?](#pip)

[chromedriver 설치 - 설치되어있는 크롬 버전과 맞추기](https://sites.google.com/a/chromium.org/chromedriver/downloads)



---



##### 동작 테스트

```
from selenium import webdriver

browser = webdriver.Chrome('C:/Users/설치경로/Downloads/chromedriver.exe')
browser.get('https://www.google.com')
browser.close()
```

---

##### error : chrome과 chrome browser의 버전을 맞춰줘야함

```
Traceback (most recent call last):
  File "C:\Users\설치경로\Desktop\testttt.py", line 11, in <module>
    browser = webdriver.Chrome('C:/Users/설치경로/Downloads/chromedriver.exe')
  File "C:\Users\설치경로\AppData\Roaming\Python\Python38\site-packages\selenium\webdriver\chrome\webdriver.py", line 76, in __init__
    RemoteWebDriver.__init__(
  File "C:\Users\설치경로\AppData\Roaming\Python\Python38\site-packages\selenium\webdriver\remote\webdriver.py", line 157, in __init__
    self.start_session(capabilities, browser_profile)
  File "C:\Users\설치경로\AppData\Roaming\Python\Python38\site-packages\selenium\webdriver\remote\webdriver.py", line 252, in start_session
    response = self.execute(Command.NEW_SESSION, parameters)
  File "C:\Users\설치경로\AppData\Roaming\Python\Python38\site-packages\selenium\webdriver\remote\webdriver.py", line 321, in execute
    self.error_handler.check_response(response)
  File "C:\Users\설치경로\AppData\Roaming\Python\Python38\site-packages\selenium\webdriver\remote\errorhandler.py", line 242, in check_response
    raise exception_class(message, screen, stacktrace)
selenium.common.exceptions.SessionNotCreatedException: Message: session not created: This version of ChromeDriver only supports Chrome version 86
Current browser version is 85.0.4183.121 with binary path C:\Program Files (x86)\Google\Chrome\Application\chrome.exe


```


---
##### google url 분석

```
https://www.google.com/search?
q=Exclamation+mark+png
&tbm=isch				// 여기까지만 해도 잘 작동한다
&ved=2ahUKEwi-16Tc2YHsAhVtGKYKHVyWBWcQ2-cCegQIABAA
&oq=Exclamation+mark+png
&gs_lcp=CgNpbWcQAzIECCMQJzICCAAyBggAEAcQHjIGCAAQBxAeMgYIABAHEB4yBggAEAcQHjIGCAAQBxAeMgYIABAHEB4yBggAEAcQHjIGCAAQBxAeUK8LWK8LYLkNaABwAHgAgAF1iAF1kgEDMC4xmAEAoAEBqgELZ3dzLXdpei1pbWfAAQE
&sclient=img
&ei=roRsX77IBO2wmAXcrJa4Bg
&bih=1040
&biw=1048
&hl=ko
```



---

### pip

파이썬의 패키지 설치 및 관리가 가능한 패키지 관리자 (Package Manager)

Pip Install Packages 의 약자

`pip install` : 패키지 설치

`pip uninstal` :   패키지 제거

`pip list` : 설치된 패키지들의 리스트 조회



> ###### Windows cmd에서 pip 사용이 안될 때
>
> 1.  Python 설치 경로 내부 /Scripts 경로에서 실행
> 2. 환경 변수 설정에 `C:\Program Files\Python\Python버전정보\Scripts` 추가 후 실행
