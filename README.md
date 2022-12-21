# 20221220


# CppCheck
## 커맨드라인 실행
```
cppcheck  --enable=all --inconclusive --xml --xml-version=2 src 2> cppcheck.xml
```

## MISRA 분석을 위한 실행
### 사전조건
Python 설치

### Misra_2012.txt 파일 복사
- 위치: C:\DevTools\misra

### 설정 파일 생성: misra.json
- 위치: C:\DevTools\misra
- 파일 구성
```
{
    "script": "misra.py",
    "args": [
        "--rule-texts=C:\\DevTools\\misra\\Misra_2012.txt"
    ]
}
```

### 실행명령
```
cppcheck.exe --addon="C:\DevTools\misra\misra.json"  --xml --xml-version=2 . 2> cppcheck.xml
```
