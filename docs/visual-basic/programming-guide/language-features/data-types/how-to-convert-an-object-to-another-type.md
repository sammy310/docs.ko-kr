---
title: '방법: 개체를 다른 형식으로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393963"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>방법: Visual Basic에서 Object를 다른 형식으로 변환
`Object` [CType 함수와](../../../language-reference/functions/ctype-function.md)같은 변환 키워드를 사용 하 여 변수를 다른 데이터 형식으로 변환할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 변수를 및으로 변환 합니다 `Object` `Integer` `String` .  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 `Object`변수의 내용이 특정 데이터 형식이 면 변수를 해당 데이터 형식으로 변환 하는 것이 좋습니다. 변수를 계속 사용 하는 경우 `Object` *boxing* 및 *unboxing* (값 형식) 또는 *런타임 바인딩* (참조 형식)이 발생 합니다. 이러한 작업은 모두 추가 실행 시간을 사용 하 고 성능이 저하 됩니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Object>
- [Visual Basic의 형식 변환](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](implicit-and-explicit-conversions.md)
- [문자열과 다른 형식 사이의 변환](conversions-between-strings-and-other-types.md)
- [배열 규칙](array-conversions.md)
- [구조체](structures.md)
- [데이터 형식](../../../language-reference/data-types/index.md)
- [형식 변환 함수](../../../language-reference/functions/type-conversion-functions.md)
