---
description: '자세한 정보: 특성'
title: 특성
ms.date: 10/22/2008
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 1557ba0945da0c8498c67f70ba4a01dd0bbe432e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642424"
---
# <a name="attributes"></a>특성

<xref:System.Attribute?displayProperty=nameWithType>는 사용자 지정 특성을 정의하는 데 사용되는 기본 클래스입니다.

 특성은 어셈블리, 형식, 멤버, 매개 변수와 같은 프로그래밍 요소에 추가할 수 있는 주석입니다. 이러한 특성은 어셈블리의 메타데이터에 저장되며 리플렉션 API를 사용하여 런타임에 액세스할 수 있습니다. 예를 들어 프레임워크는 형식이나 멤버에 적용하여 해당 형식이나 멤버가 사용되지 않음을 나타낼 수 있는 <xref:System.ObsoleteAttribute>를 정의합니다.

 특성에는 특성과 관련된 추가 데이터를 전달하는 하나 이상의 속성이 있을 수 있습니다. 예를 들어 `ObsoleteAttribute`는 형식이나 멤버가 사용되지 않는 릴리스에 대한 추가 정보 및 사용되지 않는 API를 대체하는 새 API에 대한 설명을 전달할 수 있습니다.

 특성의 일부 속성은 특성을 적용할 때 지정해야 합니다. 이러한 속성은 위치 생성자 매개 변수로 표시되기 때문에 필수 속성 또는 필수 인수라고 합니다. 예를 들어 <xref:System.Diagnostics.ConditionalAttribute>의 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 속성은 필수 속성입니다.

 특성을 적용할 때 반드시 지정하지 않아도 되는 속성은 선택적 속성(또는 선택적 인수)이라고 합니다. 이러한 속성은 설정 가능한 속성으로 표시됩니다. 컴파일러는 특성을 적용할 때 이러한 속성을 설정하는 특수 구문을 제공합니다. 예를 들어 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 선택적 인수를 나타냅니다.

 ✔️ “Attribute” 접미사를 사용하여 사용자 지정 특성 클래스의 이름을 지정하세요.

 ✔️ 사용자 지정 특성에 <xref:System.AttributeUsageAttribute>를 적용하세요.

 ✔️ 선택적 인수에 설정 가능한 속성을 제공하세요.

 ✔️ 필수 인수에 가져오기 전용 속성을 제공하세요.

 ✔️ 필수 인수에 해당하는 속성을 초기화하려면 생성자 매개 변수를 제공하세요. 각 매개 변수는 해당 속성과 동일한 이름(다른 대/소문자 사용)을 사용해야 합니다.

 ❌ 선택적 인수에 해당하는 속성을 초기화하려면 생성자 매개 변수를 제공하면 안 됩니다.

 즉, 생성자와 setter 둘 다로 설정할 수 있는 속성이 없습니다. 이 지침을 사용하면 선택적인 인수와 필수 인수가 매우 명시적으로 구분되며 동일한 작업을 수행하는 데 두 가지 방법을 사용할 필요가 없습니다.

 ❌ 사용자 지정 특성 생성자를 오버로드하면 안 됩니다.

 생성자가 하나만 있는 경우 필수 인수와 선택적 인수가 사용자에게 명확하게 전달됩니다.

 ✔️ 가능하면 사용자 지정 특성 클래스를 봉인하세요. 그러면 특성을 더 빠르게 조회할 수 있습니다.

 *Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
