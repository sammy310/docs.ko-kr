---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 2a1dd19189ff65413255b9bc137e1a7f0227bbe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716644"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
지정 된 어셈블리에서 네임 스페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`namespaceList`|필수 가져올 쉼표로 구분 된 네임 스페이스 목록입니다.|  
  
## <a name="remarks"></a>주의  
 `-imports` 옵션은 현재 소스 파일 집합 또는 참조 된 어셈블리에서 정의 된 네임 스페이스를 가져옵니다.  
  
 `-imports` 지정 된 네임 스페이스의 멤버는 컴파일할 때 모든 소스 코드 파일에서 사용할 수 있습니다. [Imports 문 (.Net 네임 스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 을 사용 하 여 단일 소스 코드 파일에서 네임 스페이스를 사용 합니다.  
  
|Visual Studio 통합 개발 환경에서을 설정 하려면|  
|---|  
|1. **솔루션 탐색기**에서 프로젝트를 선택 합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2. **참조** 탭을 클릭 합니다.<br />3. **사용자 가져오기 추가** 단추 옆의 상자에 네임 스페이스 이름을 입력 합니다.<br />4. **사용자 가져오기 추가** 단추를 클릭 합니다.|  
  
## <a name="example"></a>예  
 다음 코드는 `-imports:system.globalization`가 지정 될 때 컴파일됩니다. 이를 사용 하지 않으면 성공적으로 컴파일할 때 `Imports System.Globalization` 문이 소스 코드 파일의 시작 부분에 포함 되거나 속성이 `System.Globalization.CultureInfo.CurrentCulture.Name`으로 정규화 되어야 합니다.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
