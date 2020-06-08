---
title: '방법: 명령줄 컴파일러 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 6def53d4a2d15dda3e3ac43abe35b3100f456fe9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408610"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>방법: 명령줄 컴파일러 호출(Visual Basic)

명령줄(MS-DOS 프롬프트라고도 함)에서 실행 파일의 이름을 입력하여 명령줄 컴파일러를 호출할 수 있습니다. 기본 Windows 명령 프롬프트에서 컴파일하는 경우 실행 파일의 정규화된 경로를 입력해야 합니다. 이 기본 동작을 재정의하려면 Visual Studio용 개발자 명령 프롬프트를 사용하거나 PATH 환경 변수를 수정할 수 있습니다. 두 방법 모두 컴파일러 이름을 입력하기만 하면 모든 디렉터리에서 컴파일할 수 있습니다.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Visual Studio용 개발자 명령 프롬프트를 사용하여 컴파일러를 호출하려면

1. Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.

2. Visual studio가 설치되어 있는 경우 Visual Studio용 개발자 명령 프롬프트를 사용하여 컴퓨터의 모든 디렉터리에서 컴파일러에 액세스할 수 있습니다.

3. Visual Studio용 개발자 명령 프롬프트를 호출합니다.

4. 명령줄에서 `vbc.exe` *sourceFileName*을 입력한 다음 ENTER 키를 누릅니다.

    예를 들어 `SourceFiles`라는 디렉터리에 소스 코드를 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 이 디렉터리로 변경합니다. 디렉터리에 `Source.vb`라는 소스 파일이 포함된 경우 `vbc.exe Source.vb`를 입력하여 컴파일할 수 있습니다.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>PATH 환경 변수를 Windows 명령 프롬프트의 컴파일러로 설정하려면

1. Windows 검색 기능을 사용하여 로컬 디스크에서 Vbc.exe를 찾습니다.

    컴파일러가 있는 디렉터리의 정확한 이름은 Windows 디렉터리의 위치와 설치된 ".NET Framework"의 버전에 따라 달라집니다. ".NET Framework" 버전이 둘 이상 설치되어 있는 경우 사용할 버전(일반적으로 최신 버전)을 결정해야 합니다.

2. **시작** 메뉴에서 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 클릭합니다.

3. **고급** 탭을 클릭한 다음 **환경 변수**를 클릭합니다.

4. **시스템** 변수 창의 목록에서 **경로**를 선택하고 **편집**을 클릭합니다.

5. **시스템 변수 편집** 대화 상자의 **변수 값** 필드에서 삽입 지점을 문자열의 끝 부분으로 이동하여 세미콜론(;)을 입력한 다음 1단계에서 찾은 전체 디렉터리 이름을 입력합니다.

6. **확인**을 클릭하여 편집 내용을 확인하고 대화 상자를 닫습니다.

     PATH 환경 변수를 변경한 후에는 컴퓨터의 모든 디렉터리로부터 Windows 명령 프롬프트에서 Visual Basic 컴파일러를 실행할 수 있습니다.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Windows 명령 프롬프트를 사용하여 컴파일러를 호출하려면

1. **시작** 메뉴에서 **보조프로그램** 폴더를 클릭하고 **Windows 명령 프롬프트**를 엽니다.

2. 명령줄에서 `vbc.exe`*sourceFileName*을 입력한 다음 ENTER 키를 누릅니다.

     예를 들어 `SourceFiles`라는 디렉터리에 소스 코드를 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 이 디렉터리로 변경합니다. 디렉터리에 `Source.vb`라는 소스 파일이 포함된 경우 `vbc.exe Source.vb`를 입력하여 컴파일할 수 있습니다.

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [조건부 컴파일](../../programming-guide/program-structure/conditional-compilation.md)
