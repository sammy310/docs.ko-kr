---
description: '자세한 정보: 구조체 디자인'
title: 구조체 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: a28dd3e452d22e61d95ec521fdbde6539e38ed78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641904"
---
# <a name="struct-design"></a>구조체 디자인

범용 값 형식은 대개 구조체, 즉 C# 키워드라고 합니다. 이 섹션에서는 일반적인 구조체 디자인에 대한 지침을 제공합니다.

 ❌ 구조체에 대해 매개 변수가 없는 생성자를 제공하지 마세요.

 이 지침에 따르면 배열의 각 항목에서 생성자를 실행하지 않고도 구조체의 배열을 만들 수 있습니다. C#에서는 구조체에 매개 변수가 없는 생성자를 사용할 수 없습니다.

 ❌ 변경 가능한 값 형식을 정의하지 마세요.

 변경 가능한 값 형식에는 여러 가지 문제가 있습니다. 예를 들어 속성 getter에서 값 형식을 반환하는 경우 호출자는 복사본을 받습니다. 복사본은 암시적으로 만들어지기 때문에 개발자는 원래 값이 아닌 복사본을 변경하고 있다는 사실을 인식할 수 없습니다. 또한 역참조되는 경우 로컬 변수도 복사본을 만들 수 있으므로 일부 언어(특히 동적 언어)에서는 변경 가능한 값 형식을 사용하는 데 문제가 있습니다.

 ✔️ 상황에 따라 모든 인스턴스 데이터가 0, false 또는 null로 설정된 상태가 유효한지 확인하세요.

 그러면 구조체의 배열이 만들어질 때 실수로 잘못된 인스턴스가 만들어지는 것을 방지할 수 있습니다.

 ✔️ 값 형식에서 <xref:System.IEquatable%601>을 구현하세요.

 값 형식의 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 메서드로 인해 boxing이 발생하고 기본 구현은 리플렉션을 사용하기 때문에 그다지 효율적이지 않습니다. <xref:System.IEquatable%601.Equals%2A>는 훨씬 더 향상된 성능을 제공하며 boxing이 발생하지 않도록 구현할 수 있습니다.

 ❌ <xref:System.ValueType>을 명시적으로 확장하지 마세요. 실제로 대부분의 언어에서 이러한 확장을 방지합니다.

 일반적으로 구조체는 매우 유용할 수 있지만 자주 boxing되지 않을 작고 변경 불가능한 단일 값에만 사용해야 합니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임워크 디자인 지침](index.md)
- [클래스와 구조체 간의 선택](choosing-between-class-and-struct.md)
