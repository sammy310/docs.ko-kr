---
title: 컴파일러 옵션 사전순 목록
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: 19e14953c08f90ea1ab245fa3124a462ccba162f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408740"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Visual Basic 컴파일러 옵션 사전순 목록
Visual Basic IDE(통합 개발 환경)에서 프로그램을 컴파일하는 대신 Visual Basic 명령줄 컴파일러를 사용할 수 있습니다. 다음은 사전순으로 정렬된 Visual Basic 명령줄 컴파일러 옵션 목록입니다.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|옵션|용도|  
|------------|-------------|  
|[@(지시 파일 지정)](specify-response-file.md)|지시 파일을 지정합니다.|  
|[-?](help.md)|컴파일러 옵션을 표시합니다. 이 명령은 `-help` 옵션 지정과 같습니다. 컴파일이 수행되지 않습니다.|  
|`-additionalfile`|코드 생성에 직접 영향을 주지 않지만 오류 또는 경고를 생성하기 위해 분석기에서 사용할 수 있는 추가 파일에 이름을 지정합니다.|  
|[-addmodule](addmodule.md)|컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.|  
|`-analyzer`|이 어셈블리에서 분석기를 실행합니다(약식: -a).|  
|[-baseaddress](baseaddress.md)|DLL의 기본 주소를 지정합니다.|  
|[-bugreport](bugreport.md)|쉽게 버그를 보고할 수 있도록 정보가 포함된 파일을 만듭니다.|  
|`-checksumalgorithm:<alg>`|PDB에 저장된 소스 파일 체크섬을 계산하기 위한 알고리즘을 지정합니다.  지원되는 값은 다음과 같습니다. SHA1(기본값) 또는 SHA256. <br>SHA1 관련 충돌 문제로 인해 SHA256 이상을 사용하는 것이 좋습니다.|  
|[-codepage](codepage.md)|컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.|  
|[-debug](debug.md)|디버깅 정보를 생성합니다.|  
|[-define](define.md)|조건부 컴파일 기호를 정의합니다.|  
|[-delaysign](delaysign.md)|어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.|  
|[-deterministic](deterministic.md)|입력이 동일한 경우 컴파일 간에 이진 콘텐츠가 동일한 어셈블리를 컴파일러에서 출력하도록 합니다.|
|[-doc](doc.md)|XML 파일에 대해 문서 주석을 처리합니다.|  
|[-errorreport](errorreport.md)|Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고하는 방식을 지정합니다.|  
|[-filealign](filealign.md)|출력 파일의 섹션에 맞출 위치를 지정합니다.|  
|[-help](help.md)|컴파일러 옵션을 표시합니다. 이 명령은 `-?` 옵션 지정과 같습니다. 컴파일이 수행되지 않습니다.|  
|[-highentropyva](highentropyva.md)|특정 실행 파일이 높은 엔트로피 ASLR(Address Space Layout Randomization)을 지원하는지 여부를 나타냅니다.|  
|[-imports](imports.md)|지정된 어셈블리에서 네임스페이스를 가져옵니다.|  
|[-keycontainer](keycontainer.md)|어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.|  
|[-keyfile](keyfile.md)|어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.|  
|[-langversion](langversion.md)|언어 버전 지정: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-libpath](libpath.md)|[-reference](reference.md) 옵션에서 참조되는 어셈블리의 위치를 지정합니다.|  
|[-linkresource](linkresource.md)|관리되는 리소스에 대한 링크를 만듭니다.|  
|[-main](main.md)|시작 시 사용할 `Sub Main` 프로시저를 포함하는 클래스를 지정합니다.|  
|[-moduleassemblyname](moduleassemblyname.md)|모듈이 속할 어셈블리의 이름을 지정합니다.|  
|`-modulename:<string>`|소스 모듈의 이름을 지정합니다.|  
|[-netcf](netcf.md)|.NET Compact Framework를 대상으로 하는 컴파일러를 설정합니다.|  
|[-noconfig](noconfig.md)|Vbc.rsp로 컴파일하지 않습니다.|  
|[-nologo](nologo.md)|컴파일러 배너 정보를 표시하지 않습니다.|  
|[-nostdlib](nostdlib.md)|컴파일러에서 표준 라이브러리를 참조하지 않도록 합니다.|  
|[-nowarn](nowarn.md)|컴파일러에서 경고를 생성하지 않도록 합니다.|  
|[-nowin32manifest](nowin32manifest.md)|실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시합니다.|  
|[-optimize](optimize.md)|코드 최적화를 사용하거나 사용하지 않도록 설정합니다.|  
|[-optioncompare](optioncompare.md)|문자열 비교가 이진인지 또는 로캘별 텍스트 의미 체계를 사용해야 하는지를 지정합니다.|  
|[-optionexplicit](optionexplicit.md)|명시적 변수 선언이 있어야 합니다.|  
|[-optioninfer](optioninfer.md)|변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.|  
|[-optionstrict](optionstrict.md)|언어 의미 체계를 엄격하게 확인합니다.|  
|[-out](out.md)|출력 파일을 지정합니다.|  
|<code>-parallel[+&#124;-]</code>|동시 빌드(+)를 사용할지 여부를 지정합니다.|  
|[-platform](platform.md)|출력 파일에 대한 컴파일러 대상으로 프로세서 플랫폼을 지정합니다.|  
|`-preferreduilang`|기본 출력 언어 이름을 지정합니다.|  
|[-quiet](quiet.md)|컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.|  
|[-recurse](recurse.md)|하위 디렉터리에서 컴파일할 소스 파일을 검색합니다.|  
|[-reference](reference.md)|어셈블리에서 메타데이터를 가져옵니다.|  
|[/refonly](refonly-compiler-option.md)|참조 어셈블리만 출력합니다.|
|[/refout](refout-compiler-option.md)|참조 어셈블리의 출력 경로를 지정합니다.|
|[-removeintchecks](removeintchecks.md)|정수 오버플로 검사를 사용하지 않습니다.|  
|[-resource](resource.md)|관리되는 리소스를 어셈블리에 포함합니다.|  
|[-rootnamespace](rootnamespace.md)|모든 형식 선언에 대한 네임스페이스를 지정합니다.|  
|`-ruleset:<file>`|특정 진단을 사용하지 않는 규칙 집합 파일을 지정합니다.|  
|[-sdkpath](sdkpath.md)|Mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.|  
|[-subsystemversion](subsystemversion.md)|생성된 실행 파일이 사용할 수 있는 하위 시스템의 최소 버전을 지정합니다.|  
|[-target](target.md)|출력 파일의 형식을 지정합니다.|  
|[-utf8output](utf8output.md)|UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.|  
|[-vbruntime](vbruntime.md)|컴파일러에서 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하거나 특정 런타임 라이브러리를 참조하여 컴파일하도록 지정합니다.|  
|[-verbose](verbose.md)|컴파일하는 동안 추가 정보를 출력합니다.|  
|[-warnaserror](warnaserror.md)|경고를 오류로 승격합니다.|  
|[-win32icon](win32icon.md)|출력 파일에 .ico 파일을 삽입합니다.|  
|[-win32manifest](win32manifest.md)|프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 애플리케이션 매니페스트 파일을 식별합니다.|  
|[-win32resource](win32resource.md)|출력 파일에 Win32 리소스를 삽입합니다.|  
  
## <a name="see-also"></a>참조

- [Visual Basic 컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
