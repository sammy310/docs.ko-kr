---
title: /debug(Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 9bf7170cee31f92481b15fb1227f21895cd3734d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827980"
---
# <a name="-debug-visual-basic"></a>-디버그 (Visual Basic)
컴파일러에서 디버깅 정보를 생성 하 여 출력 파일에 배치 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. 지정 `+` 또는 `/debug` 컴파일러에서 디버깅 정보를 생성 하는.pdb 파일에 저장 합니다. 지정 `-` 지정 하지 않는 것과 동일한 결과가 `/debug`합니다.|  
|`full` &#124; `pdbonly`|선택 사항입니다. 컴파일러에서 생성되는 디버깅 정보 형식을 지정합니다. 지정 하지 않는 경우 `/debug:pdbonly`, 기본값은 `full`, 실행 중인 프로그램에 디버거를 연결할 수 있습니다. `pdbonly` 인수를 사용 하면 소스 코드 디버깅 디버거에서 프로그램이 시작 될 때 실행 중인 프로그램이 디버거에 연결 되는 경우에 어셈블리 언어 코드가 표시 됩니다.|  
  
## <a name="remarks"></a>설명  
 디버그 빌드를 만들려면 이 옵션을 사용합니다. 지정 하지 않는 경우 `/debug`, `/debug+`, 또는 `/debug:full`, 프로그램의 출력 파일을 디버그할 수 없습니다.  
  
 기본적으로 디버깅 정보 생성 되지는 (`/debug-`). 내보낼 디버깅 정보 지정 `/debug` 또는 `/debug+`합니다.  
  
 애플리케이션의 디버그 성능을 구성하는 방법에 대한 자세한 내용은 [쉽게 디버깅할 수 있도록 이미지 만들기](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md)를 참조하세요.  
  
|설정-Visual Studio 통합된 개발 환경에서 디버그|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급 컴파일 옵션**을 클릭합니다.<br />4.  값을 수정 합니다 **디버그 정보 생성** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 출력 파일에 디버깅 정보를 저장 합니다. `App.exe`합니다.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
