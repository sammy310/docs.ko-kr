---
title: Mid 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581483"
---
# <a name="mid-statement"></a>Mid 문
@No__t_0 변수의 지정 된 문자 수를 다른 문자열의 문자로 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>요소  
 `Target`  
 필수 요소. 수정할 `String` 변수의 이름입니다.  
  
 `Start`  
 필수 요소. `Integer` 식입니다. 텍스트 바꾸기가 시작 되는 `Target`의 문자 위치입니다. `Start`는 1부터 사용 하는 인덱스를 사용 합니다.  
  
 `Length`  
 (선택 사항) `Integer` 식입니다. 바꿀 문자 수입니다. 생략 하면 모든 `String` 사용 됩니다.  
  
 `StringExpression`  
 필수 요소. `Target`의 일부를 대체 하는 `String` 식입니다.  
  
## <a name="exceptions"></a>예외  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 또는 `Length` < 0입니다.|  
  
## <a name="remarks"></a>주의  
 대체 되는 문자 수는 항상 `Target`의 문자 수보다 작거나 같습니다.  
  
 Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수와 `Mid` 문이 있습니다. 이러한 요소는 모두 문자열에서 지정 된 수의 문자에서 작동 하지만 `Mid` 문이 문자를 대체 하는 동안 `Mid` 함수는 문자를 반환 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>을 참조하십시오.  
  
> [!NOTE]
> 이전 버전의 Visual Basic `MidB` 문은 문자열이 아닌 바이트 단위로 대체 합니다. 더블 바이트 문자 집합 (DBCS) 애플리케이션의 문자열을 변환에 주로 사용 됩니다. 모든 Visual Basic 문자열은 유니코드 이며 `MidB`는 더 이상 지원 되지 않습니다.  
  
## <a name="example"></a>예제  
 이 예에서는 `Mid` 문을 사용 하 여 문자열 변수의 지정 된 문자 수를 다른 문자열의 문자로 바꿉니다.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>요구 사항  
 **네임 스페이스:** [microsoft.visualbasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:** `Strings`  
  
 **어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.visualbasic)  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Visual Basic의 문자열 소개](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
