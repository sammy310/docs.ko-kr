---
title: Null 조건 연산자
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 003f579a7128bbe2462b7fbe7057de03e61bfbe6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348295"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. 하거나? () null 조건 연산자 (Visual Basic)

멤버 액세스 (`?.`) 또는 인덱스 (`?()`) 작업을 수행 하기 전에 null (`Nothing`)의 왼쪽 피연산자 값을 테스트 합니다. 왼쪽 피연산자가 `Nothing`로 계산 되 면 `Nothing`을 반환 합니다. 일반적으로 값 형식을 반환 하는 식에서 null 조건 연산자는 <xref:System.Nullable%601>을 반환 합니다.

이러한 연산자는 null 검사를 처리 하는 코드를 작성 하는 데 도움이 됩니다. 특히 데이터 구조체로 내림차순으로 사용할 수 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

비교를 위해 null 조건 연산자가 없는 첫 번째 식의 대체 코드는 다음과 같습니다.

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

경우에 따라 null 일 수 있는 개체에 대 한 작업을 수행 해야 합니다 (예: 부울 속성은 다음 예제에서 `IsAllowedFreeShipping`).

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

다음과 같이 null 조건 연산자를 사용 하 여 코드를 줄이고 null을 수동으로 확인 하지 않을 수 있습니다.

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Null 조건부 연산자는 단락 연산자입니다.  조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 `Nothing`반환 하는 경우 나머지 체인 실행이 중지 됩니다.  다음 예에서는 `A`, `B`또는 `C`가 `Nothing`으로 계산 되는 경우 `C(E)` 평가 되지 않습니다.

```vb
A?.B?.C?(E)
```

Null 조건부 멤버 액세스의 또 다른 용도는 훨씬 낮은 코드를 사용 하 여 스레드로부터 안전한 방식으로 대리자를 호출 하는 것입니다.  다음 예제에서는 `NewsBroadcaster` 및 `NewsReceiver`의 두 가지 형식을 정의 합니다. 뉴스 항목은 `NewsBroadcaster.SendNews` 대리자에 의해 수신자에 게 전송 됩니다.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

`SendNews` 호출 목록에 요소가 없으면 `SendNews` 대리자는 <xref:System.NullReferenceException>을 throw 합니다. Null 조건부 연산자 앞에 다음과 같은 코드는 대리자 호출 목록이 `Nothing`되지 않도록 합니다.

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

새로운 방식은 훨씬 더 간단합니다.

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

새로운 방식은 컴파일러가 `SendNews`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다. null 조건부 대리자 호출 구문 `Invoke`가 없기 때문에 `SendNews?(String)` 메서드를 명시적으로 호출해야 합니다.

## <a name="see-also"></a>참고자료

- [연산자 (Visual Basic)](index.md)
- [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)
- [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)
