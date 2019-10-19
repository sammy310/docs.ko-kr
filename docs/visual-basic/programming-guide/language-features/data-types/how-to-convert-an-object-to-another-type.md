---
title: '방법: Visual Basic에서 Object를 다른 형식으로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 39083fc55d30e24c357ec162a15466f81655f4c8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582334"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>방법: Visual Basic에서 Object를 다른 형식으로 변환
[CType 함수와](../../../../visual-basic/language-reference/functions/ctype-function.md)같은 변환 키워드를 사용 하 여 `Object` 변수를 다른 데이터 형식으로 변환할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Object` 변수를 `Integer` 및 `String` 변환 합니다.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 @No__t_0 변수의 내용이 특정 데이터 형식이 면 변수를 해당 데이터 형식으로 변환 하는 것이 좋습니다. @No__t_0 변수를 계속 사용 하는 경우 *boxing* 및 *unboxing* (값 형식) 또는 *런타임 바인딩* (참조 형식)이 발생 합니다. 이러한 작업은 모두 추가 실행 시간을 사용 하 고 성능이 저하 됩니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Object>
- [Visual Basic 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [문자열과 다른 형식 사이의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [배열 규칙](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)
- [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
