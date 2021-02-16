---
description: '자세한 정보: 예외 Throw'
title: 예외 Throw
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: b1cf7a4eecc32a9f76ea06c47dd6c16d3afe5470
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642138"
---
# <a name="exception-throwing"></a>예외 Throw

이 섹션에서 설명하는 예외 Throw 지침에서는 실행 실패의 의미를 제대로 정의해야 합니다. 실행 실패는 멤버가 수행하도록 설계된 작업(멤버 이름이 암시하는 작업)을 수행할 수 없을 때마다 발생합니다. 예를 들어 `OpenFile` 메서드가 열린 파일 핸들을 호출자에게 반환할 수 없는 경우 실행 실패로 간주됩니다.

 대부분의 개발자는 0으로 나누기 또는 null 참조와 같은 사용 오류에 예외를 편안하게 사용해 왔습니다. 프레임워크에서 예외는 실행 오류를 포함한 모든 오류 조건에 사용됩니다.

 ❌ 오류 코드를 반환하지 마세요.

 예외는 프레임워크에서 오류를 보고하는 기본 방법입니다.

 ✔️ 예외를 throw하여 실행 실패를 보고하세요.

 ✔️ 코드에서 추가 실행에 안전하지 않은 상황이 발생하는 경우 예외를 throw하는 대신 `System.Environment.FailFast`(.NET Framework 2.0 기능)를 호출하여 프로세스를 종료하는 것이 좋습니다.

 ❌ 가능하면 일반적인 제어 흐름에는 예외를 사용하지 마세요.

 시스템 오류와 경합 상태가 발생할 수 있는 작업을 제외하면 프레임워크 디자이너는 사용자가 예외를 throw하지 않는 코드를 작성할 수 있도록 API를 디자인해야 합니다. 예를 들어 사용자가 예외를 throw하지 않는 코드를 작성할 수 있도록 멤버를 호출하기 전에 사전 조건을 확인하는 방법을 제공할 수 있습니다.

 다른 멤버의 사전 조건을 확인하는 데 사용되는 멤버를 종종 tester라고 하며, 실제로 작업을 수행하는 멤버를 doer라고 합니다.

 경우에 따라 Tester-Doer 패턴에 허용되지 않는 성능 오버헤드가 있을 수 있습니다. 이런 경우 소위 Try-Parse 패턴을 사용하는 것이 좋습니다(자세한 내용은 [예외 및 성능](exceptions-and-performance.md) 참조).

 ✔️ 예외 throw가 성능이 미치는 영향을 고려하세요. 초당 100을 초과하는 throw 비율은 대부분의 애플리케이션 성능에 현저한 영향을 미칠 수 있습니다.

 ✔ 시스템 오류가 아닌 멤버 계약의 위반️으로 인해 공개적으로 호출 가능한 멤버에서 throw된 모든 예외를 문서화하고 계약의 일부로 처리하세요.

 계약의 일부인 예외에서는 한 버전을 다음 버전으로 변경할 수 없습니다. 즉, 예외 형식을 변경할 수 없으며 새 예외를 추가할 수도 없습니다.

 ❌ 일부 옵션에 따라 throw되거나 throw되지 않는 퍼블릭 멤버가 없도록 하세요.

 ❌ 반환 값이나 `out` 매개 변수로 예외를 반환하는 퍼블릭 멤버가 없도록 하세요.

 예외를 throw하는 대신 퍼블릭 API에서 예외를 반환하면 예외 기반 오류 보고의 많은 혜택을 사용할 수 없게 됩니다.

 ✔️ 예외 작성기 메서드를 사용하는 것이 좋습니다.

 여러 위치에서 동일한 예외를 throw하는 것이 일반적입니다. 코드 블로트를 방지하려면 예외를 만들고 해당 속성을 초기화하는 도우미 메서드를 사용하세요.

 또한 예외를 throw하는 멤버는 인라인되지 않습니다. 작성기 내에서 throw 문을 이동하면 멤버가 인라인될 수 있습니다.

 ❌ 예외 필터 블록에서 예외를 throw하지 마세요.

 예외 필터에서 예외가 발생하면 예외는 CLR에서 catch되고 필터는 false를 반환합니다. 이 동작은 실행되어 명시적으로 false를 반환하는 필터와 구분할 수 없으므로 디버그하기가 매우 어렵습니다.

 ❌ finally 블록에서 예외를 명시적으로 throw하면 안 됩니다. throw되는 메서드 호출 결과로 암시적으로 throw되는 예외는 허용됩니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [예외 디자인 지침](exceptions.md)
