---
description: 에 대해 자세히 알아보세요. 하거나? () null 조건 연산자 (Visual Basic)
title: Null 조건 연산자
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 558b8921d0da4089505dd1035cb6039af24a2802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665369"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. 하거나? () null 조건 연산자 (Visual Basic)

`Nothing`멤버 액세스 () 또는 인덱스 () 작업을 수행 하기 전에 null ()의 왼쪽 피연산자 값을 테스트 `?.` `?()` 하 고, `Nothing` 왼쪽 피연산자가로 계산 되 면를 반환 `Nothing` 합니다. 일반적으로 값 형식을 반환 하는 식에서 null 조건 연산자는를 반환 합니다 <xref:System.Nullable%601> .

이러한 연산자는 null 검사를 처리 하는 코드를 작성 하는 데 도움이 됩니다. 특히 데이터 구조체로 내림차순으로 사용할 수 있습니다. 다음은 그 예입니다. 

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

다음 예제의 부울 속성과 같이 해당 개체에 대 한 부울 멤버의 값을 기반으로 하 여 null 일 수 있는 개체에 대 한 작업을 수행 해야 하는 경우가 있습니다 `IsAllowedFreeShipping` .

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

Null 조건부 연산자는 단락 연산자입니다.  조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업이 반환 `Nothing` 되 면 나머지 체인 실행이 중지 됩니다.  다음 예에서는, `C(E)` `A` 또는가 `B` `C` 로 계산 되는 경우이 계산 되지 않습니다 `Nothing` .

```vb
A?.B?.C?(E)
```

Null 조건부 멤버 액세스의 또 다른 용도는 훨씬 낮은 코드를 사용 하 여 스레드로부터 안전한 방식으로 대리자를 호출 하는 것입니다.  다음 예제에서는 및 라는 두 가지 형식을 정의 합니다 `NewsBroadcaster` `NewsReceiver` . 뉴스 항목은 대리자에 의해 수신자에 게 전송 됩니다 `NewsBroadcaster.SendNews` .

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

호출 목록에 요소가 없으면 `SendNews` `SendNews` 대리자는을 throw <xref:System.NullReferenceException> 합니다. Null 조건부 연산자 이전에 다음과 같은 코드는 대리자 호출 목록이이 아닌 것으로 확인 되었습니다 `Nothing` .

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

새로운 방식은 컴파일러가 `SendNews`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다. null 조건부 대리자 호출 구문 `SendNews?(String)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.

## <a name="see-also"></a>참고 항목

- [연산자(Visual Basic)](index.md)
- [Visual Basic 프로그래밍 가이드](../../programming-guide/index.md)
- [Visual Basic 언어 참조](../index.md)
