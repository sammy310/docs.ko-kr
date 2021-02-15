---
description: '자세한 정보: 예외 및 성능'
title: 예외 및 성능
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 72b35ccca5514e56dcc04fc0a07d1f9887c4a2f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642125"
---
# <a name="exceptions-and-performance"></a>예외 및 성능

예외와 관련된 한 가지 일반적인 문제는 정기적으로 실패하는 코드에 예외를 사용할 경우 구현 성능이 저하될 수 있다는 점입니다. 이는 유효한 우려입니다. 멤버가 예외를 throw하는 경우 성능이 현저하게 저하될 수 있습니다. 그러나 오류 코드 사용을 허용하지 않는 예외 지침을 엄격하게 준수하면 성능을 향상할 수 있습니다. 이 섹션에서 설명하는 두 가지 패턴은 이렇게 하는 방법을 제안합니다.

 ❌ 예외로 인해 성능이 저하될 수 있으므로 오류 코드를 사용하지 마세요.

 성능을 향상하려면 다음 두 섹션에서 설명하는 Tester-Doer 패턴이나 Try-Parse 패턴을 사용할 수 있습니다.

## <a name="tester-doer-pattern"></a>Tester-Doer 패턴

 경우에 따라 예외 throw 멤버의 성능은 멤버를 둘로 구분하여 향상할 수 있습니다. <xref:System.Collections.Generic.ICollection%601> 인터페이스의 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드를 살펴보겠습니다.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 `Add` 메서드는 컬렉션이 읽기 전용인 경우에 throw됩니다. 따라서 메서드 호출이 자주 실패할 것으로 예상되는 시나리오에서는 성능 문제가 될 수 있습니다. 문제를 완화하는 방법 중 하나는 값을 추가하기 전에 컬렉션이 쓰기 가능한지를 테스트하는 것입니다.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 조건을 테스트하는 데 사용되는 멤버를 tester라고 하며, 이 예제에서는 `IsReadOnly` 속성입니다. 잠재적으로 throw되는 작업을 수행하는 데 사용되는 멤버를 doer라고 하며, 이 예제에서는 `Add` 메서드입니다.

 ✔️ 예외와 관련된 성능 문제를 방지하려면 일반적인 시나리오에서 예외를 throw할 수 있는 멤버에 Tester-Doer 패턴을 사용하는 것이 좋습니다.

## <a name="try-parse-pattern"></a>Try-Parse 패턴

 성능이 매우 중요한 API에서는 이전 섹션에서 설명한 Tester-Doer 패턴보다 훨씬 더 빠른 패턴을 사용해야 합니다. 이 패턴은 멤버 이름 조정을 요청하여 잘 정의된 테스트 사례를 멤버 의미 체계의 일부로 만듭니다. 예를 들어 <xref:System.DateTime>은 문자열의 구문 분석이 실패할 경우 예외를 throw하는 <xref:System.DateTime.Parse%2A> 메서드를 정의합니다. 구문 분석을 시도하는 해당 <xref:System.DateTime.TryParse%2A> 메서드도 정의하지만 구문 분석이 실패할 경우 false를 반환하고 `out` 매개 변수를 사용하여 성공한 구문 분석의 결과를 반환합니다.

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 이 패턴을 사용할 때는 엄격한 조건으로 try 기능을 정의하는 것이 중요합니다. 잘 정의된 try 이외의 이유로 멤버가 실패할 경우 멤버는 해당 예외를 계속 throw해야 합니다.

 ✔️ 예외와 관련된 성능 문제를 방지하려면 일반적인 시나리오에서 예외를 throw할 수 있는 멤버에 Try-Parse 패턴을 사용하는 것이 좋습니다.

 ✔️ 이 패턴을 구현하는 메서드에 접두사 “Try” 및 부울 반환 형식을 사용하세요.

 ✔ Try-Parse 패턴을 사용하는 각 멤버에 대해 예외 throw 멤버를 제공하세요.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [예외 디자인 지침](exceptions.md)
