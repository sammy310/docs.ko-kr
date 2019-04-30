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
author: KrzysztofCwalina
ms.openlocfilehash: f9fe3045d8bd8b4d625c5cd49bc18574ebb740de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026434"
---
# <a name="exceptions-and-performance"></a>예외 및 성능
예외와 관련 된 한 가지 일반적인 문제는 예외를 지속적으로 실패 하는 코드를 사용 하는 경우 구현의 성능은 허용 되지 경우 이 맞는 말입니다. 멤버에서 예외를 throw 하는 경우 해당 성능이 크기가 커져 느린 수 있습니다. 그러나 오류 코드를 사용 하 여 허용 하지 않는 예외 지침을 준수할 엄격 하 게 하는 동안 적절 한 성능을 달성 하는 것이 같습니다. 이 섹션에서 설명 하는 두 가지 패턴에는이 작업을 수행 하는 방법을 제안 합니다.  
  
 **X DO NOT** 있는지 예외 영향을 줄 수 성능 저하 문제 때문에 오류 코드를 사용 합니다.  
  
 성능 향상을 위해 Tester-doer 패턴 또는 다음 두 섹션에 설명 된 구문 분석 시도 패턴을 사용 하는 것이 같습니다.  
  
## <a name="tester-doer-pattern"></a>Tester-doer 패턴  
 경우에 따라 성능 예외를 throw 할 멤버의 멤버를 두 개로 분할 하 여 개선할 수 있습니다. 살펴보겠습니다 합니다 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드는 <xref:System.Collections.Generic.ICollection%601> 인터페이스입니다.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 메서드가 `Add` 컬렉션이 읽기 전용 이면 throw 됩니다. 이 종종 실패 메서드 호출이 필요한 시나리오에서 성능 문제를 수 있습니다. 문제를 완화 하는 방법 중 하나는 값을 추가 하기 전에 컬렉션에 쓸 수 있는지 여부를 테스트 합니다.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 예에서 속성인는 조건을 테스트 하는 데 사용 하는 멤버 `IsReadOnly`, 테스터가 라고 합니다. 잠재적으로 throwing 작업을 수행 하는 데 사용 된 멤버는 `Add` 예제의 메서드를 벗어났을 라고 합니다.  
  
 **✓ CONSIDER** Tester-doer 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
## <a name="try-parse-pattern"></a>구문 분석 시도 패턴  
 성능이 매우 중요 한 Api에 대 한 이전 섹션에서 설명한 Tester-doer 패턴 보다는 훨씬 빠른 패턴을 사용 해야 합니다. 멤버 의미 체계의 일부 경우 잘 정의 된 테스트 하기 위해 멤버 이름의 조정에 대 한 패턴을 호출 합니다. 예를 들어 <xref:System.DateTime> 정의 <xref:System.DateTime.Parse%2A> 문자열의 구문 분석 하지 못하면 예외가 throw 되는 메서드. 또한 해당 정의 <xref:System.DateTime.TryParse%2A> 메서드를 구문 분석 하려고 하지만 false를 반환 합니다 구문 분석 실패 하 고 사용 하 여 성공적으로 구문 분석 결과 반환 하는 경우는 `out` 매개 변수입니다.  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 이 패턴을 사용 하는 경우에 엄격한 용어로 시도 기능을 정의 해야 합니다. 잘 정의 된 try 이외의 어떤 이유로 든 실패 하면 멤버 멤버는 해당 하는 예외가 계속 throw 해야 합니다.  
  
 **✓ CONSIDER** Try 구문 분석 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
 **✓ DO** 이 패턴을 구현 하는 방법에 대 한 접두사 "Try" 및 Boolean 반환 형식을 사용 합니다.  
  
 **✓ DO** Try 구문 분석 패턴을 사용 하 여 각 멤버에 대 한 예외 throw 멤버를 제공 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## <a name="see-also"></a>참고자료

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
