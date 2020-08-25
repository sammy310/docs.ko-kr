---
title: 컴파일러 옵션
description: 'F # 컴파일러의 명령줄 옵션을 사용 하 여 F # 앱 및 라이브러리의 컴파일을 제어 합니다.'
ms.date: 08/15/2020
ms.openlocfilehash: c10808e97d31bd3bdb469fc2a8e57a4650170dec
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812148"
---
# <a name="compiler-options"></a>컴파일러 옵션

이 항목에서는 fsc.exe F # 컴파일러에 대 한 컴파일러 명령줄 옵션에 대해 설명 합니다.

프로젝트 속성을 설정 하 여 컴파일 환경을 제어할 수도 있습니다. .NET Core를 대상으로 하는 프로젝트의 경우의 "기타 플래그" 속성은 `<OtherFlags>...</OtherFlags>` `.fsproj` 추가 명령줄 옵션을 지정 하는 데 사용 됩니다.

## <a name="compiler-options-listed-alphabetically"></a>컴파일러 옵션 사전순 목록

다음 표에서는 사전순으로 나열 된 컴파일러 옵션을 보여 줍니다. F # 컴파일러 옵션 중 일부는 c # 컴파일러 옵션과 유사 합니다. 이 경우 c # 컴파일러 옵션 항목에 대 한 링크가 제공 됩니다.

|컴파일러 옵션|Description|
|---------------|-----------|
|`-a filename.fs`|지정 된 파일에서 라이브러리를 생성 합니다. 이 옵션은의 약식 형태입니다 `--target:library filename.fs` .|
|`--baseaddress:address`|DLL을 로드할 기본 설정 기준 주소를 지정합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;baseaddress &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)을 참조 하세요.|
|`--codepage:id`|필요한 페이지가 시스템의 현재 기본 코드 페이지가 아닌 경우 컴파일하는 동안 사용할 코드 페이지를 지정 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;코드 페이지 &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/codepage-compiler-option.md)를 참조 하세요.|
|`--consolecolors`|오류 및 경고가 콘솔에서 색으로 구분 된 텍스트를 사용 하도록 지정 합니다.|
|`--crossoptimize[+|-]`|크로스 모듈 최적화를 사용 하거나 사용 하지 않도록 설정 합니다.|
|<code>--delaysign[+&#124;-]</code>|강력한 이름 키의 공개 부분만 사용 하 여 어셈블리 서명을 연기 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;delaysign &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 참조 하세요.|
|<code>--checked[+&#124;-]</code>|오버플로 검사 생성을 사용 하거나 사용 하지 않도록 설정 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;checked &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/checked-compiler-option.md)를 참조 하세요.|
|<code>--debug[+&#124;-]</code><br /><br /><code>-g[+&#124;-]</code><br /><br /><code>--debug:[full&#124;pdbonly]</code><br /><br /><code>-g: [full&#124;pdbonly]</code>|디버그 정보 생성을 사용 하거나 사용 하지 않도록 설정 하거나 생성할 디버그 정보의 형식을 지정 합니다. 기본값은 `full` 로, 실행 중인 프로그램에 연결할 수 있습니다. `pdbonly`Pdb (프로그램 데이터베이스) 파일에 저장 된 제한 된 디버깅 정보를 가져오려면 선택 합니다.<br /><br />같은 이름의 c # 컴파일러 옵션과 동일 합니다. 자세한 내용은 다음을 참조하세요.<br /><br />[ 디버그 &#40;C&#35; 컴파일러 옵션&#41;를&#47;](../../csharp/language-reference/compiler-options/debug-compiler-option.md)합니다.|
|`--define:symbol`<br /><br />`-d:symbol`|조건부 컴파일에 사용 되는 기호를 정의 합니다.|
|<code>--deterministic[+&#124;-]</code>|결정적 어셈블리 (모듈 버전 GUID 및 타임 스탬프 포함)를 생성 합니다. 이 옵션은 와일드 카드 버전 번호와 함께 사용할 수 없으며 포함 및 이식 가능한 디버깅 형식만 지원 합니다.|
|`--doc:xmldoc-filename`|지정 된 파일에 XML 문서 주석을 생성 하도록 컴파일러에 지시 합니다. 자세한 내용은 [XML Documentation](xml-documentation.md)을 참조하세요.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;doc &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/doc-compiler-option.md)을 참조 하세요.|
|`--fullpaths`|정규화 된 경로를 생성 하도록 컴파일러에 지시 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;fullpaths &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)을 참조 하세요.|
|`--help`<br /><br />`-?`|모든 컴파일러 옵션에 대 한 간략 한 설명을 포함 하 여 사용 정보를 표시 합니다.|
|<code>--highentropyva[+&#124;-]</code>|강화 된 보안 기능인 높은 엔트로피 주소 공간 레이아웃 임의 설정 (ASLR)을 사용 하거나 사용 하지 않도록 설정 합니다. OS는 응용 프로그램 (예: 스택 및 힙)의 인프라가 로드 되는 메모리의 위치를 임의화 합니다. 이 옵션을 사용 하도록 설정 하면 운영 체제에서이 임의 설정을 사용 하 여 64 비트 컴퓨터에서 전체 64 비트 주소 공간을 사용할 수 있습니다.|
|`--keycontainer:key-container-name`|강력한 이름의 키 컨테이너를 지정합니다.|
|`--keyfile:filename`|생성 된 어셈블리에 서명 하는 데 사용할 공개 키 파일의 이름을 지정 합니다.|
|`--lib:folder-name`<br /><br />`-I:folder-name`|참조 되는 어셈블리를 검색할 디렉터리를 지정 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;lib &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/lib-compiler-option.md)를 참조 하세요.|
|`--linkresource:resource-info`|지정 된 리소스를 어셈블리에 연결 합니다. 리소스 정보 형식은입니다. <code>filename[name[public&#124;private]]</code><br /><br />이 옵션을 사용 하 여 단일 리소스를 연결 하는 대신 옵션을 사용 하 여 전체 리소스 파일을 포함할 수 `--resource` 있습니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;linkresource &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)을 참조 하세요.|
|`--mlcompatibility`|다른 ML 버전과의 호환성을 위해 디자인 된 기능을 사용할 때 표시 되는 경고를 무시 합니다.|
|`--noframework`|.NET Framework 어셈블리에 대 한 기본 참조를 사용 하지 않도록 설정 합니다.|
|`--nointerfacedata`|F # 관련 메타 데이터를 포함 하는 어셈블리에 일반적으로 추가 되는 리소스를 생략 하도록 컴파일러에 지시 합니다.|
|`--nologo`|컴파일러를 시작할 때 배너 텍스트를 표시 하지 않습니다.|
|`--nooptimizationdata`|인라인 구문을 구현 하는 데 필요한 최적화만 포함 하도록 컴파일러에 지시 합니다. 크로스 모듈 인라인 처리를 금지 하지만 이진 호환성이 향상 됩니다.|
|`--nowin32manifest`|기본 Win32 매니페스트를 생략 하도록 컴파일러에 지시 합니다.|
|`--nowarn:warning-number-list`|숫자로 나열 된 특정 경고를 사용 하지 않도록 설정 합니다. 각 경고 번호를 쉼표로 구분 합니다. 컴파일 출력에서 경고에 대 한 경고 번호를 검색할 수 있습니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;nowarn &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)을 참조 하세요.|
|<code>--optimize[+&#124;-][optimization-option-list]</code><br /><br /><code>-O[+&#124;-] [optimization-option-list]</code>|최적화를 사용 하거나 사용 하지 않도록 설정 합니다. 일부 최적화 옵션을 나열 하 여 선택적으로 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 여기에는 `nojitoptimize` , `nojittracking` , `nolocaloptimize` , `nocrossoptimize` , `notailcalls` 등이 있습니다.|
|`--out:output-filename`<br /><br />`-o:output-filename`|컴파일된 어셈블리 또는 모듈의 이름을 지정 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;out &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/out-compiler-option.md)을 참조 하세요.|
|`--pathmap:path=sourcePath,...`|실제 경로를 컴파일러에서 출력되는 소스 경로 이름에 매핑하는 방법을 지정합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;pathmap &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/pathmap-compiler-option.md)을 참조 하세요.|
|`--pdb:pdb-filename`|출력 디버그 PDB (프로그램 데이터베이스) 파일의 이름을로 합니다. 이 옵션 `--debug` 은가 사용 하도록 설정 된 경우에만 적용 됩니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;pdb &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/pdb-compiler-option.md)을 참조 하세요.|
|`--platform:platform-name`|생성 된 코드가 지정 된 플랫폼 에서만 실행 되도록 지정 합니다 ( `x86` , `Itanium` 또는 `x64` ). 또는 플랫폼 이름을 선택 하는 경우 생성 된 `anycpu` 코드를 모든 플랫폼에서 실행할 수 있도록 지정 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;platform &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/platform-compiler-option.md)을 참조 하세요.|
|`--preferreduilang:lang`| 기본 출력 언어 문화권 이름을 지정 합니다 (예:  `es-ES` , `ja-JP` ). |
|`--quotations-debug`|F # 인용 리터럴에서 파생 된 정의와 리플렉션 정의에서 파생 된 식에 대 한 추가 디버깅 정보를 내보내도록 지정 합니다. 디버그 정보는 F # 식 트리 노드의 사용자 지정 특성에 추가 됩니다. [코드 인용](code-quotations.md) 및 [Expr. customattributes](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html#CustomAttributes)를 참조 하세요.|
|`--reference:assembly-filename`<br /><br />`-r:assembly-filename`|컴파일하는 코드에서 F # 또는 .NET Framework 어셈블리의 코드를 사용할 수 있도록 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;참조 &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/reference-compiler-option.md)을 참조 하세요.|
|`--resource:resource-filename`|관리 되는 리소스 파일을 생성 된 어셈블리에 포함 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;리소스 &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조 하세요.|
|`--sig:signature-filename`|생성 된 어셈블리를 기반으로 서명 파일을 생성 합니다. 서명 파일에 대 한 자세한 내용은 [서명](signature-files.md)을 참조 하세요.|
|`--simpleresolution`|MSBuild 확인이 아닌 디렉터리 기반 Mono 규칙을 사용 하 여 어셈블리 참조를 확인 하도록 지정 합니다. 기본값은 Mono에서 실행 하는 경우를 제외 하 고 MSBuild 해상도를 사용 하는 것입니다.|
|`--standalone`|F # 라이브러리와 같은 추가 어셈블리를 요구 하지 않고 자체적으로 실행 되도록 모든 종속성을 포함 하는 어셈블리를 생성 하도록 지정 합니다.|
|`--staticlink:assembly-name`|지정 된 어셈블리와이 어셈블리에 종속 된 모든 참조 Dll을 정적으로 연결 합니다. DLL 이름이 아니라 어셈블리 이름을 사용 합니다.|
|`--subsystemversion`|생성 된 실행 파일에서 사용할 OS 하위 시스템의 버전을 지정 합니다. Windows 7의 경우 6.02, 6.01의 경우 Windows 8.1, Windows Vista의 경우 6.00을 사용 합니다. 이 옵션은 Dll이 아닌 실행 파일에만 적용 되며 응용 프로그램이 특정 버전의 OS 에서만 사용 가능한 특정 보안 기능에 종속 되는 경우에만 사용 해야 합니다. 이 옵션을 사용 하는 경우 사용자가 더 낮은 버전의 OS에서 응용 프로그램을 실행 하려고 하면 오류 메시지와 함께 실패 하 게 됩니다.|
|<code>--tailcalls[+&#124;-]</code>|테일 IL 명령을 사용 하거나 사용 하지 않도록 설정 하 여 tail 재귀 함수에 대해 스택 프레임을 다시 사용 하도록 설정 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.|
|<code>--target:[exe&#124;winexe&#124;library&#124;module] filename</code>|생성 된 컴파일된 코드의 형식 및 파일 이름을 지정 합니다.<ul><li>`exe` 콘솔 응용 프로그램을 의미 합니다.<br /></li><li>`winexe` 는 표준 입력/출력 스트림 (stdin, stdout 및 stderr)이 정의 되지 않는다는 점에서 콘솔 응용 프로그램과는 다른 Windows 응용 프로그램을 의미 합니다.<br /></li><li>`library` 는 진입점이 없는 어셈블리입니다.<br /></li><li>`module` 는 나중에 다른 모듈과 함께 어셈블리로 결합할 수 있는 모듈 (.netmodule) .NET Framework입니다.<br /></li><ul/>이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;target &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/target-compiler-option.md)을 참조 하세요.|
|`--times`|컴파일의 타이밍 정보를 표시 합니다.|
|`--utf8output`|UTF-8 인코딩으로 인쇄 컴파일러 출력을 사용 하도록 설정 합니다.|
|`--warn:warning-level`|경고 수준 (0-5)을 설정 합니다. 기본 수준은 3입니다. 각 경고에는 심각도를 기준으로 하는 수준이 지정 됩니다. 수준 5는 수준 1 보다 더 심각 하지만 심각 하지 않은 경고를 제공 합니다.<br /><br />수준 5 경고는 21 (런타임에 재귀적으로 확인 됨), 22 ( `let rec` 순서가 잘못 됨), 45 (전체 추상화) 및 52 (방어 복사본)입니다. 다른 모든 경고는 수준 2입니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;경고 &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/warn-compiler-option.md)을 참조 하세요.|
|`--warnon:warning-number-list`|기본적으로 해제 되거나 다른 명령줄 옵션에 의해 해제 될 수 있는 특정 경고를 사용 하도록 설정 합니다. 1182 (사용 되지 않는 변수) 경고는 기본적으로 해제 되어 있습니다.|
|<code>--warnaserror[+&#124;-] [warning-number-list]</code>|경고를 오류로 보고 하는 옵션을 사용 하거나 사용 하지 않도록 설정 합니다. 특정 경고 번호를 제공 하 여 사용 하지 않도록 설정 하거나 설정할 수 있습니다. 명령줄에서 나중에 옵션은 명령줄의 이전 옵션을 재정의 합니다. 예를 들어 오류로 보고 하지 않을 경고를 지정 하려면를 지정 `--warnaserror+` `--warnaserror-:warning-number-list` 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;warnaserror &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)을 참조 하세요.|
|`--win32manifest:manifest-filename`|Win32 매니페스트 파일을 컴파일에 추가 합니다. 이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;win32manifest &#40;C&#35; 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)을 참조 하세요.|
|`--win32res:resource-filename`|컴파일에 Win32 리소스 파일을 추가 합니다.<br /><br />이 컴파일러 옵션은 같은 이름의 c # 컴파일러 옵션과 같습니다. 자세한 내용은 [&#47;win32res (&#40;C&#35;) 컴파일러 옵션&#41;](../../csharp/language-reference/compiler-options/win32res-compiler-option.md)를 참조 하세요.|

## <a name="related-articles"></a>관련 문서

|제목|Description|
|-----|-----------|
|[F# Interactive 옵션](fsharp-interactive-options.md)|fsi.exe F # 인터프리터에서 지 원하는 명령줄 옵션을 설명 합니다.|
|[프로젝트 속성 참조](/visualstudio/ide/reference/project-properties-reference)|빌드 옵션을 제공 하는 프로젝트 속성 페이지를 비롯 하 여 프로젝트에 대 한 UI를 설명 합니다.|
