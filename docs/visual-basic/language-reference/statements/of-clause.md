---
title: Of 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: c0cfbb5109d5b49f995028944e735c96440c9ab2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583503"
---
# <a name="of-clause-visual-basic"></a>Of 절(Visual Basic)
*제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저에서 *형식 매개 변수* 를 식별 하는 `Of` 절을 소개 합니다. 제네릭 형식에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)을 참조 하세요.  
  
## <a name="using-the-of-keyword"></a>Of 키워드 사용  
 다음 코드 예제에서는 `Of` 키워드를 사용 하 여 두 개의 형식 매개 변수를 사용 하는 클래스의 개요를 정의 합니다. @No__t_2 인터페이스를 사용 하 여 `keyType` 매개 변수를 *제한* 합니다. 즉, 사용 하는 코드에서 <xref:System.IComparable>를 구현 하는 형식 인수를 제공 해야 합니다. @No__t_0 프로시저가 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 메서드를 호출할 수 있도록이 작업이 필요 합니다. 제약 조건에 대한 자세한 내용은 [Type List](../../../visual-basic/language-reference/statements/type-list.md)을 참조하세요.  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 위의 클래스 정의를 완료 하는 경우 여기에서 다양 한 `dictionary` 클래스를 생성할 수 있습니다. @No__t_0 및 `keyType`에 제공 하는 형식은 클래스에서 보유 하는 항목의 형식과 각 항목에 연결 하는 키 형식을 결정 합니다. 제약 조건 때문에 <xref:System.IComparable>를 구현 하는 형식을 `keyType`를 제공 해야 합니다.  
  
 다음 코드 예제에서는 `String` 항목을 보유 하는 개체를 만들고 `Integer` 키를 각각 연결 합니다. `Integer`는 <xref:System.IComparable>를 구현 하므로 `keyType`의 제약 조건을 충족 합니다.  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 `Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참조

- <xref:System.IComparable>
- [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
