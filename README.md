# VS Code C/C++ Build and Debug Configuration

macOS용 VS Code에서 Clang으로 C/C++ 프로그램을 빌드하고 LLDB로 디버깅하기 위한 설정 파일 모음입니다.

## 구성

`C/for mac/` 아래에 다음 설정이 있습니다.

- `tasks.json`: C/C++ 빌드 및 실행 작업
- `launch.json`: LLDB 디버깅 설정

## 제공되는 작업

- 현재 C 파일을 Clang으로 빌드
- 같은 디렉터리의 여러 C 파일을 함께 빌드
- 현재 C++ 파일을 Clang++으로 빌드
- 생성된 실행 파일 실행

빌드 결과는 소스 파일과 같은 디렉터리에 확장자 없이 생성됩니다.

## 준비 사항

- macOS
- Visual Studio Code
- `clang`, `clang++`, LLDB
- `lldb` 디버거를 제공하는 VS Code 확장 프로그램, 예: [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb)

```bash
clang --version
clang++ --version
lldb --version
```

## 사용 방법

1. 프로젝트에 `.vscode` 디렉터리를 만들고 설정 파일을 복사합니다.
2. C/C++ 파일을 엽니다.
3. VS Code의 **Terminal → Run Build Task...** 에서 필요한 빌드 작업을 선택합니다.
4. 실행은 `execute` 작업 또는 다음 명령으로 수행합니다.

   ```bash
   ./main
   ```

5. 디버깅 전에는 먼저 프로그램을 빌드한 뒤 **Run and Debug**를 시작합니다.

## 참고 사항

- `launch.json`에는 자동 빌드(`preLaunchTask`)가 없으므로 디버깅 전에 직접 빌드해야 합니다.
- 여러 파일 빌드는 현재 디렉터리의 `.c` 파일을 대상으로 합니다.
- 기존 작업 이름에 `bulid` 오타가 포함되어 있으므로 VS Code에서 작업을 선택할 때 이름을 그대로 사용해야 합니다.
