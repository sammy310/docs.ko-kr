---
title: Optional(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 67ceedffecdfba8ec0c2829a3af31d194f18bd88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820791"
---
# <a name="optional-visual-basic"></a>Optional(Visual Basic)
프로시저를 호출할 때 프로시저 인수를 생략할 수를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 각 선택적 매개 변수에 상수 식 해당 매개 변수의 기본 값으로 지정 해야 합니다. 식이 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), 값 데이터 형식의 기본 값 매개 변수의 기본값으로 사용 됩니다.  
  
 선택적 매개 변수를 포함 하는 매개 변수 목록에서 오는 모든 매개 변수를 선택적 여야 합니다.  
  
 `Optional` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
-   [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  선택적 매개 변수 없이 프로시저를 호출할 때에 위치 또는 이름으로 인수를 전달할 수 있습니다. 자세한 내용은 [위치 및 이름별 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)합니다.  
  
> [!NOTE]
>  또한 오버 로드를 사용 하 여 선택적 매개 변수가 있는 프로시저를 정의할 수 있습니다. 하나의 선택적 매개 변수를 사용 하는 경우에 두 가지 오버 로드 된 버전의 프로시저 매개 변수를 허용 하는 하나, 하나는 정의할 수 있습니다. 자세한 내용은 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 선택적 매개 변수가 있는 프로시저를 정의 합니다.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 이름으로 전달 된 인수를 사용 하 여 프로시저 위치에서 전달 된 인수를 사용 하 여 호출 하는 방법에 설명 합니다. 프로시저에 두 개의 선택적 매개 변수입니다.  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a>참고자료

- [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)
- [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
