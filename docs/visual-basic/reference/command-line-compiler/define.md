---
title: -정의 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: c21223cc353b7a4614511aa97340c6bc5d61e70e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200660"
---
# <a name="-define-visual-basic"></a>-정의 (Visual Basic)
조건부 컴파일러 상수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`symbol`|필수 요소. 정의할 기호입니다.|  
|`value`|선택 사항입니다. `symbol`을 할당할 값입니다. 하는 경우 `value` 문자열은 백슬래시/따옴표 시퀀스로 묶어야 (\\") 따옴표 대신 합니다. 값을 지정하지 않으면 True가 지정됩니다.|  
  
## <a name="remarks"></a>설명  
 `-define` 옵션은 사용과 비슷합니다는 `#Const` 사용 하 여 정의 하는 상수를 제외 하 고 원본 파일에서 전처리기 지시문 `-define` 공용 이며 프로젝트의 모든 파일에 적용 합니다.  
  
 이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.  
  
 `-d`는 약식 `-define`입니다.  
  
 쉼표를 사용해 기호 정의를 구분하여 `-define`으로 여러 기호를 정의할 수 있습니다.  
  
|Visual Studio 통합 개발 환경에서 /define을 설정하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급**을 클릭합니다.<br />4.  값을 수정 합니다 **사용자 지정 상수** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>참고자료
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
