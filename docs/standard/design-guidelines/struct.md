---
title: 구조체 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: c6ac53014e048da3a90dd7b8e961176f61e90355
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290813"
---
# <a name="struct-design"></a>구조체 디자인
일반적으로 일반 용도의 값 형식을 구조체, c # 키워드 라고 합니다. 이 단원에서는 일반적인 구조체 디자인에 대 한 지침을 제공 합니다.

 ❌구조체에 대해 매개 변수가 없는 생성자를 제공 하지 마십시오.

 이 지침에 따라 배열의 각 항목에서 생성자를 실행할 필요 없이 구조체 배열을 만들 수 있습니다. C #에서는 구조체에 매개 변수가 없는 생성자를 사용할 수 없습니다.

 ❌변경할 수 있는 값 형식을 정의 하지 마십시오.

 변경 가능한 값 형식에는 여러 가지 문제가 있습니다. 예를 들어, getter 속성에서 값 형식을 반환 하는 경우 호출자는 복사본을 받습니다. 복사본이 암시적으로 만들어지므로 개발자는 원래 값이 아니라 복사본을 변경 하는 것을 인식 하지 못할 수 있습니다. 또한 일부 언어 (특히 동적 언어)에는 변경 가능한 값 형식을 사용 하는 데 문제가 있습니다 .이 경우에도 역참조 되는 경우에는 로컬 변수를 사용 하 여 복사본을 만들 수 있습니다.

 ✔️ 모든 인스턴스 데이터가 0, false 또는 null (적절 한 경우)으로 설정 된 상태 인지 확인 합니다.

 이렇게 하면 구조체의 배열을 만들 때 잘못 된 인스턴스를 실수로 생성 하지 않습니다.

 <xref:System.IEquatable%601>값 형식에 대해를 구현 ✔️ 합니다.

 <xref:System.Object.Equals%2A?displayProperty=nameWithType>값 형식에 대 한 메서드는 boxing을 발생 시키고 기본 구현은 리플렉션을 사용 하기 때문에 그다지 효율적이 지 않습니다. <xref:System.IEquatable%601.Equals%2A>는 더 나은 성능을 가질 수 있으며 boxing을 발생 시 키 지 않도록 구현할 수 있습니다.

 ❌명시적으로 확장 하지 마십시오 <xref:System.ValueType> . 실제로 대부분의 언어에서이를 방지 합니다.

 일반적으로 구조체는 매우 유용할 수 있지만 자주 boxing 되지 않는 작은 단일 불변 값에만 사용 해야 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
- [클래스와 구조체 간의 선택](choosing-between-class-and-struct.md)
