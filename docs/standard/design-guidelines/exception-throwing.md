---
title: 예외 Throw
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741668"
---
# <a name="exception-throwing"></a>예외 Throw
이 섹션에서 설명 하는 예외를 throw 하는 지침에는 실행 실패의 의미를 올바르게 정의 해야 합니다. 멤버가 수행 하도록 디자인 된 작업 (멤버 이름에서 의미 함)을 수행할 수 없을 때마다 실행 실패가 발생 합니다. 예를 들어 `OpenFile` 메서드가 열린 파일 핸들을 호출자에 게 반환할 수 없는 경우 실행 실패로 간주 됩니다.

 대부분의 개발자는 0 또는 null 참조로 나누기와 같은 사용 오류에 대 한 예외를 사용 하는 데 익숙해질 수 있습니다. 프레임 워크에서 예외는 실행 오류를 포함 하 여 모든 오류 조건에 사용 됩니다.

 ❌는 오류 코드를 반환 하지 않습니다.

 예외는 프레임 워크에서 오류를 보고 하는 기본 방법입니다.

 예외를 throw 하 여 실행 오류를 보고 ✔️ 합니다.

 ✔️ 코드에서 추가 실행에 안전 하지 않은 상황이 발생 하는 경우 예외를 throw 하는 대신 `System.Environment.FailFast` (.NET Framework 2.0 기능)를 호출 하 여 프로세스를 종료 하는 것이 좋습니다.

 가능 하면 일반적인 제어 흐름에 대 한 예외를 사용 하지 ❌ 합니다.

 시스템 오류와 경합 상태가 발생할 수 있는 작업을 제외 하 고, 프레임 워크 디자이너는 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 Api를 디자인 해야 합니다. 예를 들어 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 멤버를 호출 하기 전에 사전 조건을 확인 하는 방법을 제공할 수 있습니다.

 다른 멤버의 사전 조건을 확인 하는 데 사용 되는 멤버를 테스터 라고 하며 실제로 작업을 수행 하는 멤버를 doer 이라고 합니다.

 Doer 패턴에 허용 되지 않는 성능 오버 헤드가 있을 수 있는 경우가 있습니다. 이러한 경우에는 해당 하는 Try-catch 패턴을 고려해 야 합니다. 자세한 내용은 [예외 및 성능](../../../docs/standard/design-guidelines/exceptions-and-performance.md) 을 참조 하십시오.

 ✔️ 예외 throw의 성능 영향을 고려 합니다. 초당 100를 초과 하는 Throw 요금은 대부분의 응용 프로그램 성능에 큰 영향을 미칠 수 있습니다.

 ✔️는 시스템 오류가 아닌 멤버 계약 위반으로 인해 공개적으로 호출할 수 있는 멤버에서 throw 된 모든 예외를 문서화 하 고 계약의 일부로 처리 합니다.

 계약의 일부인 예외는 한 버전에서 다음 버전으로 변경 되어서는 안 됩니다. 즉, 예외 형식은 변경 되지 않아야 하 고 새 예외는 추가 하면 안 됩니다.

 ❌에는 일부 옵션에 따라 throw 하거나 사용할 수 없는 public 멤버가 없습니다.

 ❌은 예외를 반환 값으로 반환 하거나 `out` 매개 변수로 반환 하는 public 멤버가 없습니다.

 공용 Api에서 예외를 throw 하는 대신 예외를 반환 하면 예외 기반 오류 보고의 많은 이점이 무효화 됩니다.

 ✔️ 예외 작성기 메서드를 사용 하는 것이 좋습니다.

 일반적으로 다른 위치에서 동일한 예외를 throw 합니다. 코드의 팽창을 방지 하려면 예외를 만들고 해당 속성을 초기화 하는 도우미 메서드를 사용 합니다.

 또한 예외를 throw 하는 멤버도 인라인 되지 않습니다. 작성기 내에서 throw 문을 이동 하면 멤버가 인라인 될 수 있습니다.

 ❌ 예외 필터 블록에서 예외를 throw 하지 않습니다.

 예외 필터에서 예외가 발생 하면 CLR에서 예외를 catch 하 고 필터가 false를 반환 합니다. 이 동작은 실행 중인 필터와는 구분 되지 않으며 false를 명시적으로 반환 하므로 디버그 하기가 매우 어렵습니다.

 ❌ finally 블록에서 명시적으로 예외를 throw 하지 않습니다. Throw 되는 메서드를 호출 하 여 발생 하는 예외를 암시적으로 throw 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
