---
description: '자세한 정보: 익명 형식 정의 (Visual Basic)'
title: 익명 형식 정의
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 2e3f847f5f844e3ed6e036c26efc330a237d193f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436918"
---
# <a name="anonymous-type-definition-visual-basic"></a>익명 형식 정의(Visual Basic)

익명 형식의 인스턴스 선언에 대 한 응답으로 컴파일러는 해당 형식에 대해 지정 된 속성을 포함 하는 새 클래스 정의를 만듭니다.

## <a name="compiler-generated-code"></a>Compiler-Generated 코드

다음 정의의 경우 `product` 컴파일러는, 및 속성을 포함 하는 새 클래스 정의를 만듭니다 `Name` `Price` `OnHand` .

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

클래스 정의에는 다음과 유사한 속성 정의가 포함 되어 있습니다. `Set`키 속성에 대 한 메서드가 없습니다. 키 속성의 값은 읽기 전용입니다.

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

또한 익명 형식 정의에는 매개 변수가 없는 생성자가 포함 됩니다. 매개 변수를 필요로 하는 생성자는 허용 되지 않습니다.

익명 형식 선언에 하나 이상의 키 속성이 포함 된 경우 형식 정의는 <xref:System.Object> <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> 및에서 상속 된 세 개의 멤버를 재정의 <xref:System.Object.ToString%2A> 합니다. 키 속성이 선언 되지 않은 경우만 <xref:System.Object.ToString%2A> 재정의 됩니다. 재정의는 다음과 같은 기능을 제공 합니다.

- `Equals``True`두 익명 형식 인스턴스가 동일한 인스턴스이거나 다음 조건을 충족 하는 경우를 반환 합니다.

  - 속성의 수는 동일 합니다.

  - 속성은 같은 순서로 선언 되며 동일한 이름 및 유추 된 형식이 동일 합니다. 이름 비교는 대/소문자를 구분 하지 않습니다.

  - 속성 중 하나 이상이 키 속성 이며 `Key` 키워드는 동일한 속성에 적용 됩니다.

  - 각 해당 키 속성 쌍의 비교는를 반환 `True` 합니다.

    예를 들어 다음 예제에서는 `Equals` `True` 및에 대해서만를 반환 합니다 `employee01` `employee08` . 각 줄 앞의 주석은 새 인스턴스가 일치 하지 않는 이유를 지정 합니다 `employee01` .

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` 적절 한 고유 GetHashCode 알고리즘을 제공 합니다. 알고리즘은 키 속성만 사용 하 여 해시 코드를 계산 합니다.

- `ToString` 다음 예제와 같이 연결 된 속성 값의 문자열을 반환 합니다. 키와 키가 아닌 속성은 모두 포함 됩니다.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

익명 형식의 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌할 수 없습니다. 즉,, 또는를 사용 `.Equals` `.GetHashCode` `.ToString` 하 여 속성의 이름을 지정할 수 없습니다.

하나 이상의 키 속성을 포함 하는 익명 형식 정의도 인터페이스를 구현 합니다 <xref:System.IEquatable%601?displayProperty=nameWithType> `T` . 여기서은 익명 형식의 형식입니다.

> [!NOTE]
> 익명 형식 선언은 동일한 어셈블리에서 발생 하는 경우에만 동일한 익명 형식을 만들며, 해당 속성은 동일한 이름 및 유추 된 형식을 가지 며 속성은 동일한 순서로 선언 되며 동일한 속성이 키 속성으로 표시 됩니다.

## <a name="see-also"></a>추가 정보

- [익명 형식](anonymous-types.md)
- [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
