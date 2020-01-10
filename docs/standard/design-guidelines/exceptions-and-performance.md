---
title: 예외 및 성능
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: e3a7fa0f284ebf028a18cae37c050d7ceda9bb79
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709389"
---
# <a name="exceptions-and-performance"></a>예외 및 성능
예외와 관련 된 일반적인 문제 중 하나는 정기적으로 실패 하는 코드에 예외가 사용 되는 경우 구현의 성능이 허용 되지 않는 것입니다. 이는 유효한 문제입니다. 멤버가 예외를 throw 하는 경우 성능이 저하 될 수 있습니다. 그러나 오류 코드를 사용할 수 없도록 하는 예외 지침을 엄격 하 게 준수 하는 동시에 성능을 향상 시킬 수 있습니다. 이 섹션에서 설명 하는 두 가지 패턴은이 작업을 수행 하는 방법을 제안 합니다.

 **X DO NOT** 있는지 예외 영향을 줄 수 성능 저하 문제 때문에 오류 코드를 사용 합니다.

 성능을 향상 시키려면 다음 두 섹션에서 설명 하는 Doer 패턴 또는 Try-catch 패턴을 사용할 수 있습니다.

## <a name="tester-doer-pattern"></a>Doer 패턴
 경우에 따라 멤버를 두 개로 분리 하 여 예외 throw 멤버의 성능을 향상 시킬 수 있습니다. <xref:System.Collections.Generic.ICollection%601> 인터페이스의 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드를 살펴보겠습니다.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 컬렉션이 읽기 전용인 경우 throw 되는 메서드 `Add`입니다. 이는 메서드 호출이 자주 실패할 것으로 예상 되는 시나리오에서 성능 문제를 일으킬 수 있습니다. 문제를 완화 하는 방법 중 하나는 값을 추가 하기 전에 컬렉션을 쓸 수 있는지 여부를 테스트 하는 것입니다.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 조건을 테스트 하는 데 사용 되는 멤버입니다 .이 예제에서 `IsReadOnly`속성은 테스터 라고 합니다. 잠재적으로 throw 되는 작업을 수행 하는 데 사용 되는 멤버입니다 .이 예제에서 `Add` 메서드를 doer 라고 합니다.

 **✓ CONSIDER** Tester-doer 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.

## <a name="try-parse-pattern"></a>Try-Parse 패턴
 매우 성능에 민감한 Api의 경우 이전 섹션에서 설명한 Doer 패턴 보다 훨씬 더 빠른 패턴을 사용 해야 합니다. 패턴은 멤버 이름을 조정 하 여 잘 정의 된 테스트 사례를 멤버 의미 체계의 일부로 만드는 작업을 호출 합니다. 예를 들어 <xref:System.DateTime>는 문자열의 구문 분석이 실패 하는 경우 예외를 throw 하는 <xref:System.DateTime.Parse%2A> 메서드를 정의 합니다. 또한 구문 분석을 시도 하는 해당 <xref:System.DateTime.TryParse%2A> 메서드를 정의 하지만 구문 분석이 실패 하 고 `out` 매개 변수를 사용 하 여 성공적으로 구문 분석 한 결과를 반환 하는 경우에는 false를 반환 합니다.

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

 이 패턴을 사용 하는 경우에는 엄격한 용어로 try 기능을 정의 하는 것이 중요 합니다. 잘 정의 된 시도 이외의 이유로 멤버가 실패 하면 해당 멤버는 여전히 해당 예외를 throw 해야 합니다.

 **✓ CONSIDER** Try 구문 분석 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.

 **✓ DO** 이 패턴을 구현 하는 방법에 대 한 접두사 "Try" 및 Boolean 반환 형식을 사용 합니다.

 **✓ DO** Try 구문 분석 패턴을 사용 하 여 각 멤버에 대 한 예외 throw 멤버를 제공 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
