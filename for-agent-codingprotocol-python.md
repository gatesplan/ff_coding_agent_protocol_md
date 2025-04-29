# Python Coding Protocol for Agent
- 이 문서는 에이전트의 원활하고 균일한 Python 코딩을 위한 프로토콜이다.
- 모든 에이전트는 Python 언어 사용시 이 코딩 프로토콜을 준수해야 한다.
- 이 파일은 루트 폴더의 중앙 지침이므로 에이전트는 절대 이 파일을 수정하지 않는다.


## 중요 규칙
- 하나의 파일은 오직 하나의 함수 또는 하나의 클래스만 포함한다.
- 주석은 한 줄 이하로, 간단한 기능 설명 수준으로 작성한다. 이때 파라메터, 리턴타입 등에 대한 설명은 하지 않는다.
- 설계 단계에서 코드를 작성하거나 일일히 나열하지 않는다.


## 클래스 디렉토리 및 코드 작성 규칙
- 클래스의 파일명과 클래스명은 CamelCase로 작성한다.
- 클래스는 항상 단일 책임 원칙을 따른다.
- 주석은 한 줄 이하로, 간단한 기능 설명 수준으로 작성한다.
- 모든 클래스 메소드는 위임 구현하며, 파일 명명 규칙은 함수 또는 메소드 규칙을 따른다.
- 각 클래스는 항상 다음 디렉토리 구조를 따른다.
```
└─ClassNameDir  # CamelCase
    └─SubModuleNameDir  # CamelCase
        └─methods  # submodules methods folder when needed
        └─exceptions  # submodules exceptions folder when needed
        └─tests  # submodules tests folder when needed
        └─__init__.py
        └─for-agent-moduleinfo.md
    └─methods  # methods folder
    └─exceptions  # exceptions folder
    └─tests  # tests folder
    └─__init__.py
    └─for-agent-moduleinfo.md
    └─ClassName.py
```

## 예외
- 예외 클래스는 항상 루트의 `EnhancedException` 클래스를 상속받아야 한다.
- `EnhancedException`이 없으면, 프로젝트 시작 단계일 수 있으므로 지시자에게 알린다.
- 예외 클래스는 전용 디렉토리를 두지 않고, 발생위치의 함수나 클래스와 같은 폴더에 두어야 한다.
- 함수나 메소드 안에서 예외 처리 작업으로 인해 컨텍스트가 길어지는 것은 안 되므로, 다음 방식을 따라 예외를 처리한다.
```
try:
    has_throwable_function(..)
    
except SomeException as e:  # catch and processable
    dedicated_exception_handler(e)
except SomeException as e:  # catch but not processable
    raise e  # 아무것도 하지 않더라도 명시적으로 re-raise
    
# 만약 필요하다면..
finally:
    dedicated_finish_function(args)
    
```
- 상기 예시에서의 줄바꿈은 가독성을 위한 설계이므로 잘 지킬 것.

## 로깅
아직 미구현. 지시자의 지시가 있으면 이에 따른다.
