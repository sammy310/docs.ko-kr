---
title: -가져오기 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 075eeccc7d80943d2757a97b9a355bbea3ef9d4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833612"
---
# <a name="-imports-visual-basic"></a>-가져오기 (Visual Basic)
지정된 된 어셈블리에서 네임 스페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`namespaceList`|필수 요소. 가져올 네임 스페이스의 쉼표로 구분 된 목록입니다.|  
  
## <a name="remarks"></a>설명  
 `-imports` 옵션 현재 소스 파일 또는 모든 참조 된 어셈블리에서 집합 내에 정의 된 모든 네임 스페이스를 가져옵니다.  
  
 지정 된 네임 스페이스의 멤버 `-imports` 컴파일할 때 모든 소스 코드 파일에 사용할 수 있습니다. 사용 된 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 단일 소스 코드 파일에서 네임 스페이스를 사용 하 합니다.  
  
|설정 하려면 Visual Studio 통합된 개발 환경에서 가져오기 /|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **참조** 탭을 클릭합니다.<br />3.  옆의 상자에 네임 스페이스 이름을 입력 합니다 **사용자 가져오기 추가** 단추입니다.<br />4.  클릭 합니다 **사용자 가져오기 추가** 단추입니다.|  
  
## <a name="example"></a>예제  
 다음 코드는 경우 `/imports:system.globalization` 지정 됩니다. 없으면 성공적으로 컴파일 중에 나 필요는 `Imports System.Globalization` 소스 코드 파일의 시작 부분에 문을 포함할 또는 속성으로 정규화 되어야 `System.Globalization.CultureInfo.CurrentCulture.Name`합니다.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
