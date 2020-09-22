---
title: Of 절
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
ms.openlocfilehash: 0595356fb75fc0ac73a49622d71fe1d28fa7b648
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865904"
---
# <a name="of-clause-visual-basic"></a>Of 절(Visual Basic)

`Of` *제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저에서 *형식 매개 변수* 를 식별 하는 절을 소개 합니다. 제네릭 형식에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)을 참조 하세요.  
  
## <a name="using-the-of-keyword"></a>Of 키워드 사용  

 다음 코드 예제에서는 키워드를 사용 하 여 `Of` 두 개의 형식 매개 변수를 사용 하는 클래스의 개요를 정의 합니다. 인터페이스를 사용 하 여 매개 변수를 *제한* 합니다. 즉,를 사용 하는 `keyType` <xref:System.IComparable> 코드에서을 구현 하는 형식 인수를 제공 해야 합니다 <xref:System.IComparable> . 프로시저에서 메서드를 호출할 수 있도록이 작업이 필요 `add` <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 합니다. 제약 조건에 대한 자세한 내용은 [Type List](type-list.md)을 참조하세요.  
  
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
  
 위의 클래스 정의를 완료 하는 경우 여기에서 다양 한 클래스를 생성할 수 있습니다 `dictionary` . 사용자가 제공 하는 `entryType` 형식과 `keyType` 클래스에서 보유 하는 항목 형식 및 각 항목과 연결 되는 키 형식에 대해 결정 합니다. 제약 조건 때문에를 `keyType` 구현 하는 형식에를 제공 해야 합니다 <xref:System.IComparable> .  
  
 다음 코드 예제에서는 항목을 보유 하는 개체를 만들고 `String` 각 항목에 대 한 키를 연결 합니다 `Integer` . `Integer` 는를 구현 <xref:System.IComparable> 하므로에서 제약 조건을 충족 `keyType` 합니다.  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 `Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](class-statement.md)  
  
 [Delegate 문](delegate-statement.md)  
  
 [Function 문](function-statement.md)  
  
 [Interface 문](interface-statement.md)  
  
 [Structure 문](structure-statement.md)  
  
 [Sub 문](sub-statement.md)  
  
## <a name="see-also"></a>참조

- <xref:System.IComparable>
- [Type List](type-list.md)
- [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)
- [위치](../modifiers/in-generic-modifier.md)
- [제한이](../modifiers/out-generic-modifier.md)
