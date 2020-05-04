---
title: -target
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: d186670489ada51fced67ff9adeb73b14909b664
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716681"
---
# <a name="-target-visual-basic"></a>-target(Visual Basic)

컴파일러 출력의 형식을 지정합니다.

## <a name="syntax"></a>구문

```console
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}
```

## <a name="remarks"></a>설명

다음 표에는 `-target` 옵션의 영향이 요약되어 있습니다.

|**옵션**|**동작**|
|----------------|------------------|
|`-target:exe`|컴파일러가 콘솔 애플리케이션 실행 파일을 만들도록 합니다.<br /><br /> `-target` 옵션이 지정되지 않은 경우의 기본값입니다. 실행 파일은 .exe 확장명으로 생성됩니다.<br /><br /> `-out` 옵션을 사용하여 지정하지 않으면 `Sub Main` 프로시저가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.<br /><br /> .exe 파일로 컴파일되는 소스 코드 파일에 하나의 `Sub Main`프로시저만 필요합니다. `-main` 컴파일러 옵션을 사용하여 `Sub Main` 프로시저를 포함하는 클래스를 지정합니다.|
|`-target:library`|컴파일러가 DLL(동적 연결 라이브러리)을 만들도록 합니다.<br /><br /> .dll 확장명을 사용하여 동적 연결 라이브러리 파일을 만듭니다.<br /><br /> `-out` 옵션을 사용하여 달리 지정되지 않은 경우 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.<br /><br /> DLL을 빌드할 때 `Sub Main` 프로시저는 필요하지 않습니다.|
|`-target:module`|컴파일러가 어셈블리에 추가할 수 있는 모듈을 생성하도록 합니다.<br /><br /> 출력 파일은 .netmodule 확장명을 사용하여 생성됩니다.<br /><br /> .NET 공용 언어 런타임에서는 어셈블리가 없는 파일을 로드할 수 없습니다. 그러나 이러한 파일은 `-reference`를 사용하여 어셈블리의 어셈블리 매니페스트에 통합할 수 있습니다.<br /><br /> 한 모듈의 코드가 다른 모듈의 내부 형식을 참조하는 경우 `-reference`를 사용하여 두 모듈을 모두 어셈블리 매니페스트에 통합해야 합니다.<br /><br /> [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션은 모듈에서 메타데이터를 가져옵니다.|
|`-target:winexe`|컴파일러가 Windows 기반 애플리케이션 실행 파일을 만들도록 합니다.<br /><br /> 실행 파일은 .exe 확장명으로 생성됩니다. Windows 기반 애플리케이션은 .NET Framework 클래스 라이브러리나 Windows API를 통해 사용자 인터페이스를 제공하는 애플리케이션입니다.<br /><br /> `-out` 옵션을 사용하여 지정하지 않으면 `Sub Main` 프로시저가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.<br /><br /> .exe 파일로 컴파일되는 소스 코드 파일에 하나의 `Sub Main`프로시저만 필요합니다. 코드에 `Sub Main` 프로시저가 있는 클래스가 둘 이상 있는 경우 `-main` 컴파일러 옵션을 사용하여 `Sub Main` 프로시저를 포함하는 클래스를 지정합니다.|
|`-target:appcontainerexe`|컴파일러가 앱 컨테이너에서 실행해야 하는 Windows 기반 애플리케이션 실행 파일을 만들도록 합니다. 이 설정은 Windows 8.x 스토어 애플리케이션에 사용하도록 설계되었습니다.<br /><br /> **appcontainerexe** 설정은 [이식 가능 파일](/windows/desktop/Debug/pe-format) 파일의 특징 필드에 비트를 설정합니다. 이 비트는 앱이 앱 컨테이너에서 실행되어야 함을 나타냅니다. 이 비트가 설정된 경우 `CreateProcess` 메서드가 앱 컨테이너 밖에서 애플리케이션을 시작하려고 시도하면 오류가 발생합니다. 이 비트 설정 외에 **-target:appcontainerexe**는 **-target:winexe**와 동일합니다.<br /><br /> 실행 파일은 .exe 확장명으로 생성됩니다.<br /><br /> `-out` 옵션을 사용하여 지정하지 않으면 `Sub Main` 프로시저가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.<br /><br /> .exe 파일로 컴파일되는 소스 코드 파일에 하나의 `Sub Main`프로시저만 필요합니다. 코드에 `Sub Main` 프로시저가 있는 클래스가 둘 이상 포함되어 있는 경우 `-main` 컴파일러 옵션을 사용하여 `Sub Main` 프로시저를 포함하는 클래스를 지정합니다.|
|`-target:winmdobj`|컴파일러가 Windows 런타임 이진(.winmd) 파일로 변환할 수 있는 중간 파일을 만들도록 합니다. 관리되는 언어 프로그램뿐만 아니라 JavaScript 및 C++ 프로그램에서도 .winmd 파일을 사용할 수 있습니다.<br /><br /> 중간 파일은 winmdobj 확장명을 사용하여 만들어집니다.<br /><br /> `-out` 옵션을 사용하여 지정하지 않으면 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다. `Sub Main` 프로시저는 필요하지 않습니다.<br /><br /> .winmdobj 파일은 Windows 메타데이터(WinMD) 파일을 생성하기 위해 <xref:Microsoft.Build.Tasks.WinMDExp> 내보내기 도구에 대한 입력으로 사용되도록 설계되었습니다. WinMD 파일은 .winmd 확장명을 가지며 원본 라이브러리의 코드와 JavaScript, C++ 및 Windows 런타임에서 사용하는 WinMD 정의를 모두 포함합니다.|

`-target:module`을 지정하지 않으면 `-target`은 .NET Framework 어셈블리 매니페스트가 출력 파일에 추가되도록 합니다.

Vbc.exe의 각 인스턴스는 최대 하나의 출력 파일을 생성합니다. `-out` 또는 `-target`과 같은 컴파일러 옵션을 두 번 이상 지정하는 경우 컴파일러에서 마지막으로 처리한 내용이 적용됩니다. 컴파일의 모든 파일에 대한 정보가 매니페스트에 추가됩니다. `-target:module`을 사용하여 생성된 파일을 제외한 모든 출력 파일은 매니페스트에 어셈블리 메타데이터를 포함합니다. [Ildasm.exe(IL 디스어셈블러)](../../../framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 출력 파일에서 메타데이터를 봅니다.

`-target`의 약식은 `-t`입니다.

### <a name="to-set--target-in-the-visual-studio-ide"></a>Visual Studio IDE에서 -target을 설정하려면

1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **애플리케이션** 탭을 클릭합니다.

3. **애플리케이션 종류** 상자에서 값을 수정합니다.

## <a name="example"></a>예제

다음 코드는 `in.dll`을 만들어 `in.vb`를 컴파일합니다.

```console
vbc -target:library in.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-out(Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-reference(Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [.NET 어셈블리](../../../standard/assembly/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
