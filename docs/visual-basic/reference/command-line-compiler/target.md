---
title: -target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: c91e69e3d9f17f758990b8385f6b8d0a1c03bef6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344743"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)
컴파일러 출력의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>설명  
 다음 표에서 요약의 효과 `-target` 옵션입니다.  
  
|**옵션**|**동작**|  
|----------------|------------------|  
|`-target:exe`|컴파일러가 실행 콘솔 응용 프로그램을 만들려고 합니다.<br /><br /> 이 없는 경우 기본 옵션 `-target` 옵션을 지정 합니다. 실행 파일은 확장명이.exe 인 생성 됩니다.<br /><br /> 지정 하지 않으면 합니다 `/out` 옵션을 출력 파일 이름을 포함 하는 입력된 파일의 이름을 사용 합니다 `Sub Main` 프로시저입니다.<br /><br /> 하나의 `Sub Main` .exe 파일로 컴파일되는 소스 코드 파일의 절차가 필요 합니다. 사용 합니다 `-main` 컴파일러 옵션을 포함 하는 클래스를 지정 합니다 `Sub Main` 프로시저입니다.|  
|`-target:library`|컴파일러가 동적 연결 라이브러리 (DLL)을 만들려고 합니다.<br /><br /> 동적 연결 라이브러리 파일은.dll 확장명을 사용 하 여 생성 됩니다.<br /><br /> 지정 하지 않으면는 `-out` 옵션을 출력 파일 이름으로 첫 번째 입력된 파일의 이름을 사용 합니다.<br /><br /> DLL을 빌드할 때를 `Sub Main` 절차가 필요 하지 않습니다.|  
|`-target:module`|컴파일러가 어셈블리를 추가할 수 있는 모듈을 만듭니다.<br /><br /> 출력 파일은 확장명이.netmodule 인 생성 됩니다.<br /><br /> .NET 공용 언어 런타임 어셈블리로 없는 파일을 로드할 수 없습니다. 그러나 통합할 수 있습니다 이러한 파일 어셈블리의 어셈블리 매니페스트에 사용 하 여 `-reference`입니다.<br /><br /> 모듈을 모두를 사용 하 여 어셈블리 매니페스트에 통합 해야 한 모듈의 코드에서 다른 모듈의 내부 형식을 참조 하는 경우 `-reference`합니다.<br /><br /> 합니다 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션 모듈에서 메타 데이터를 가져옵니다.|  
|`-target:winexe`|컴파일러가 실행 가능한 Windows 기반 응용 프로그램을 만들려고 합니다.<br /><br /> 실행 파일은 확장명이.exe 인 생성 됩니다. Windows 기반 응용 프로그램을 제공 하는 것 중 하나에서 사용자 인터페이스는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 라이브러리 또는 Windows Api를 사용 하 여 합니다.<br /><br /> 지정 하지 않으면 합니다 `-out` 옵션을 출력 파일 이름을 포함 하는 입력된 파일의 이름을 사용 합니다 `Sub Main` 프로시저입니다.<br /><br /> 하나의 `Sub Main` .exe 파일로 컴파일되는 소스 코드 파일의 절차가 필요 합니다. 코드에는 둘 이상의 클래스에 있는 경우에서는 `Sub Main` 프로시저를 사용 하 여 합니다 `-main` 컴파일러 옵션을 포함 하는 클래스를 지정 합니다 `Sub Main` 프로시저|  
|`-target:appcontainerexe`|컴파일러가 실행 Windows 기반 응용 프로그램을 만들려면 앱 컨테이너에서 실행 해야 하는 합니다. 이 설정은 사용자에 사용할 [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] 응용 프로그램입니다.<br /><br /> 합니다 **appcontainerexe** 설정 비트의 특성 필드를 설정 합니다 [이식 가능한 실행](/windows/desktop/Debug/pe-format) 파일입니다. 이 비트는 앱 컨테이너에서 앱을 실행 해야 함을 나타냅니다. 이 비트가 설정 된 경우 오류가 발생 하는 경우는 `CreateProcess` 메서드는 앱 컨테이너 외부에서 응용 프로그램을 시작 하려고 합니다. 이 비트를 설정 하는 것 외 **-target: appcontainerexe** 같습니다 **-/target: winexe**합니다.<br /><br /> 실행 파일은 확장명이.exe 인 생성 됩니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면 합니다 `-out` 옵션을 출력 파일 이름을 포함 하는 입력된 파일의 이름을 사용 합니다 `Sub Main` 프로시저입니다.<br /><br /> 하나의 `Sub Main` .exe 파일로 컴파일되는 소스 코드 파일의 절차가 필요 합니다. 코드에 있는 둘 이상의 클래스를 포함 하는 경우는 `Sub Main` 프로시저를 사용 하 여 합니다 `-main` 컴파일러 옵션을 포함 하는 클래스를 지정 합니다 `Sub Main` 프로시저|  
|`-target:winmdobj`|컴파일러가 Windows 런타임 이진 (.winmd) 파일로 변환할 수 있는 중간 파일을 만듭니다. JavaScript에서.winmd 파일을 사용할 수 있습니다 하 고 C++ 관리 되는 언어 프로그램 뿐만 아니라 프로그램입니다.<br /><br /> 중간 파일.winmdobj 확장을 사용 하 여 생성 됩니다.<br /><br /> 사용 하 여 별도로 지정 하지 않으면는 `-out` 옵션을 출력 파일 이름으로 첫 번째 입력된 파일의 이름을 사용 합니다. `Sub Main` 프로시저는 필요 하지 않습니다.<br /><br /> .Winmdobj 파일에 대 한 입력으로 사용 하도록 합니다.는 <xref:Microsoft.Build.Tasks.WinMDExp> 내보내기 도구를 Windows 메타 데이터 (WinMD) 파일을 생성 합니다. WinMD 파일.winmd 확장명을 가진 및 해당 JavaScript WinMD 정의와 원본 라이브러리에서 코드를 모두 포함 C++, 및 Windows 런타임을 사용 합니다.|  
  
 지정 하지 않으면 `-target:module`, `-target` 하면를 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리 매니페스트가 출력 파일을 추가할 수 있습니다.  
  
 Vbc.exe의 각 인스턴스 생성, 최대, 한 출력 파일입니다. 와 같은 컴파일러 옵션을 지정 하면 `-out` 또는 `-target` 한 번만, 컴파일러 프로세스 발효 개가 있습니다. 컴파일에서 모든 파일에 대 한 정보를 매니페스트에 추가 됩니다. 모든 출력 파일을 사용 하 여 만든 항목을 제외한 파일 `-target:module` 매니페스트에 어셈블리 메타 데이터를 포함 합니다. 사용 하 여 [Ildasm.exe (IL 디스어셈블러)](../../../framework/tools/ildasm-exe-il-disassembler.md) 출력 파일에 메타 데이터를 볼 수 있습니다.  
  
 `-target`의 약식은 `-t`입니다.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Visual Studio IDE에서 대상 설정  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.   
  
2. **응용 프로그램** 탭을 클릭합니다.  
  
3. 값을 수정 합니다 **응용 프로그램 유형을** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드 컴파일을 `in.vb`만들기, `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-참조 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [.NET 어셈블리](../../../standard/assembly/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
