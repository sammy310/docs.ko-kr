---
title: F# Interactive 옵션
description: 지 원하는 명령줄 옵션에 알아보려면 F# Interactive, fsi.exe 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: cca1ef6671878acb1b837d6590139d5de7b7167d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996803"
---
# <a name="f-interactive-options"></a>F# Interactive 옵션

> [!NOTE]
> 이 문서에서는 현재 Windows만을 위한 환경에 대해 설명합니다.  다시 작성될 예정입니다.

이 항목에서 지 원하는 명령줄 옵션에 설명 합니다 F# 대화형 `fsi.exe`합니다. F#대화형 허용으로 동일한 명령줄 옵션의 대다수는 F# 컴파일러 있지만 사용할 수 있는 몇 가지 추가 옵션이 합니다.

## <a name="using-f-interactive-for-scripting"></a>사용 하 여 F# 대화형 스크립팅
F#대화형 `fsi.exe`, 대화형으로 실행할 수 있습니다 또는 스크립트를 실행 하려면 명령줄에서 실행할 수 있습니다. 명령줄 구문

```
> fsi.exe [options] [ script-file [arguments] ]
```

파일 확장명에 대 한 F# 스크립트 파일은 `.fsx`합니다.

## <a name="table-of-f-interactive-options"></a>목차 F# 대화형 옵션
다음 표에서 지원 옵션 F# 대화형입니다. 명령줄 또는 Visual Studio IDE를 통해 이러한 옵션을 설정할 수 있습니다. Visual Studio IDE에서 이러한 옵션을 설정 하려면 엽니다는 **도구** 메뉴에서 **옵션...** 를 차례로 확장 합니다  **F# 도구** 노드와 선택  **F# 대화형**.

목록에서 표시 되는 위치 F# 대화형 옵션 인수 목록 요소는 세미콜론으로 구분 됩니다 (`;`).

|옵션|설명|
|------|-----------|
|**--**|지시 하는 데 F# 대화형 나머지 인수에 대 한 명령줄 인수로 취급 하도록 합니다 F# 프로그램이 나 스크립트의 목록을 사용 하 여 코드에서 액세스할 수 있는 **fsi.CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--codepage:&lt;int&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--consolecolors**[**+**&#124;**-**]|경고 출력 및 오류 메시지를 색입니다.|
|**--crossoptimize**[**+**&#124;**-**]|크로스 모듈 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.|
|**--debug**[**+**&#124;**-**]<br /><br />**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--define:&lt;string&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--deterministic**[**+**&#124;**-**]|결정적 어셈블리 (모듈 버전 GUID 및 타임 스탬프 포함)를 생성 합니다.|
|**--exec**|지시 F# 대화형 명령줄에 지정 된 스크립트 파일을 실행 하거나 파일을 로드 후 종료 합니다.|
|**--fullpaths**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--gui**[**+**&#124;**-**]|사용 하거나 Windows Forms 이벤트 루프를 사용 하지 않도록 설정 합니다. 기본값은 사용입니다.|
|**--help**<br /><br />**-?**|명령줄 구문 및 각 옵션의 간략 한 설명을 표시 하는 데 사용 합니다.|
|**--lib:&lt;folder-list&gt;**<br /><br />**-I:&lt;folder-list&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--load:&lt;filename&gt;**|시작 시 주어진된 소스 코드를 컴파일하고 컴파일된 로드 F# 세션으로 생성 합니다. 대상 소스와 같은 스크립트 지시문을 포함 하는 경우 **#use** 또는 **#load**를 사용 해야 합니다 **-사용 하 여** 하거나 **#use** 대신 **-부하** 하거나 **#load**합니다.|
|**--mlcompatibility**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--noframework**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 참조 하세요. [컴파일러 옵션](compiler-options.md)|
|**--nologo**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--nowarn:&lt;warning-list&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--optimize**[**+**&#124;**-**]|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--preferreduilang:&lt;lang&gt;**| 기본 출력 언어 문화권 이름 (예를 들어, ES-ES, JA-JP)를 지정합니다. |
|**--quiet**|표시 안 함 F# Interactive의 출력을 합니다 **stdout** 스트림 합니다.|
|**--quotations-debug**|파생 되는 식에 대 한 추가 디버깅 정보를 내보내지 않아야는 지정 F# 따옴표로 묶인 리터럴 및 반영된 정의 합니다. 디버그 정보를 사용자 지정 특성에 추가 됩니다는 F# 식 트리 노드가 있습니다. 참조 [코드 인용](code-quotations.md) 하 고 [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)합니다.|
|**--readline**[**+**&#124;**-**]|대화형 모드에서 탭 완성 기능을 사용 하지 않도록 설정 하거나 사용 합니다.|
|**--reference:&lt;filename&gt;**<br /><br />**-r:&lt;filename&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--shadowcopyreferences**[**+**&#124;**-**]|참조 하 여 잠기지 않도록 합니다 F# 대화형 프로세스입니다.|
|**--simpleresolution**|MSBuild 확인 대신 디렉터리 기반의 규칙을 사용 하 여 어셈블리 참조를 확인 합니다.|
|**--tailcalls**[**+**&#124;**-**]|스택 프레임을 테일 재귀 함수에 대해 다시 사용 하면 테일 IL 명령 사용할 수 없도록 설정 하거나 사용 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.|
|**--targetprofile:&lt;string&gt;**|이 어셈블리의 대상 프레임 워크 프로필을 지정합니다. 유효한 값은 mscorlib, netcore netstandard입니다.  기본값은 mscorlib.|
|**--use:&lt;filename&gt;**|시작 시 주어진된 파일 초기 입력으로 사용할 인터프리터를 알려 줍니다.|
|**--utf8output**|Fsc.exe 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--warn:&lt;warning-level&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--warnaserror**[**+**&#124;**-**]|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|와 동일 합니다 **fsc.exe** 컴파일러 옵션입니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.|

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----|-----------|
|[컴파일러 옵션](compiler-options.md)|에 대 한 사용 가능한 명령줄 옵션에 설명 합니다 F# 컴파일러 **fsc.exe**합니다.|
