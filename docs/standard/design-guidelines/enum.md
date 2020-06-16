---
title: 열거형 디자인
description: 특수 한 종류의 값 형식인 열거형을 디자인 합니다. 단순 열거형은 작고 폐쇄형 선택 항목 집합을 보유 합니다. 플래그 열거형은 열거형 값에 대 한 비트 연산을 지원 합니다.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 40a9faf53dc8a03674cd59074244c15cd304bdd2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768539"
---
# <a name="enum-design"></a>열거형 디자인

열거형은 특수 한 종류의 값 형식입니다. 열거형에는 단순 열거형과 플래그 열거형의 두 종류가 있습니다.

단순 열거형은 작은 닫힌 선택 집합을 나타냅니다. 간단한 열거형의 일반적인 예는 색 집합입니다.

플래그 열거형은 열거형 값에 대 한 비트 연산을 지원 하도록 디자인 되었습니다. 플래그 열거의 일반적인 예는 옵션의 목록입니다.

✔️는 열거형을 사용 하 여 값 집합을 나타내는 강력한 형식 매개 변수, 속성 및 반환 값을 사용 합니다.

정적 상수 대신 열거형을 사용 하 여 ✔️ 합니다.

❌개방형 집합 (예: 운영 체제 버전, 친구 이름 등)에는 열거형을 사용 하지 마세요.

❌나중에 사용 하기 위해 예약 된 열거형 값을 제공 하지 마십시오.

이후 단계에서 항상 기존 열거형에 값을 추가할 수 있습니다. 열거형에 값을 추가 하는 방법에 대 한 자세한 내용은 [열거형에 값 추가](#add_value) 를 참조 하세요. 예약 된 값은 실제 값의 집합만 pollute 사용자 오류가 발생 하는 경향이 있습니다.

❌값이 하나만 있는 열거형은 공개적으로 노출 하지 마십시오.

이후 C Api의 확장성을 보장 하는 일반적인 방법은 메서드 시그니처에 예약 된 매개 변수를 추가 하는 것입니다. 이러한 예약 된 매개 변수는 단일 기본값을 포함 하는 열거형으로 표현 될 수 있습니다. 이는 관리 되는 Api에서 수행 하면 안 됩니다. 메서드 오버 로드를 사용 하면 이후 릴리스에서 매개 변수를 추가할 수 있습니다.

❌열거형에는 센티널 값을 포함 하지 않습니다.

개발자는 프레임 워크 개발자에 게 유용 하지만 센티널 값은 프레임 워크의 사용자에 게 혼동을 주는 경우가 많습니다. 열거형이 나타내는 집합의 값 중 하나가 아니라 열거형의 상태를 추적 하는 데 사용 됩니다.

✔️ 단순 열거형에 0 값을 제공 합니다.

"None"과 같은 값을 호출 하는 것이 좋습니다. 이러한 특정 열거형에 적절 한 값이 없는 경우 열거형의 가장 일반적인 기본값은 0의 기본 값을 할당 해야 합니다.

<xref:System.Int32>다음 중 하나에 해당 하지 않는 경우 (대부분의 프로그래밍 언어의 기본값)를 열거형의 기본 형식으로 사용 하는 것이 좋습니다 ✔️.

- 열거형이 플래그 열거형 이며 32 개 이상의 플래그를 포함 하거나 앞으로 더 많은 것이 필요 합니다.

- 다른 크기의 열거를 필요로 하는 <xref:System.Int32> 비관리 코드와의 상호 운용성을 위해 기본 형식은과 달라 야 합니다.

- 기본 형식이 작을수록 공간이 크게 절약 됩니다. 열거를 주로 제어 흐름에 대 한 인수로 사용 하는 경우 크기는 약간 차이가 있습니다. 크기 절감은 다음과 같은 경우에 중요할 수 있습니다.

  - 가장 자주 인스턴스화되는 구조체 또는 클래스에서 열거형을 필드로 사용할 것으로 간주 합니다.

  - 사용자가 많은 배열 또는 열거형 인스턴스의 컬렉션을 만들 것으로 간주 합니다.

  - 많은 수의 열거형 인스턴스가 serialize 될 것으로 간주 됩니다.

메모리 내 사용의 경우 관리 되는 개체는 항상 `DWORD` 정렬 되므로 전체 인스턴스 크기는 항상으로 반올림 되기 때문에 더 작은 열거형을 압축 하려면 인스턴스의 여러 열거형 또는 다른 작은 구조를 사용 해야 합니다 `DWORD` .

✔️ DO name은 복수 명사 또는 명사구를 사용 하는 열거형과 단일 명사 또는 명사구를 사용 하는 단순 열거형을 플래그 지정 합니다.

❌직접 확장 하지 마십시오 <xref:System.Enum?displayProperty=nameWithType> .

<xref:System.Enum?displayProperty=nameWithType>는 CLR에서 사용자 정의 열거형을 만드는 데 사용 하는 특수 한 형식입니다. 대부분의 프로그래밍 언어는이 기능에 대 한 액세스를 제공 하는 프로그래밍 요소를 제공 합니다. 예를 들어 c #에서 `enum` 키워드는 열거형을 정의 하는 데 사용 됩니다.

<a name="design"></a>

### <a name="designing-flag-enums"></a>플래그 열거형 디자인

<xref:System.FlagsAttribute?displayProperty=nameWithType>열거형에 플래그를 적용 ✔️ 합니다. 단순 열거형에는이 특성을 적용 하지 마십시오.

✔️는 플래그 열거형 값으로 2의 거듭제곱을 사용 하므로 비트 OR 연산을 사용 하 여 자유롭게 결합할 수 있습니다.

일반적으로 사용 되는 플래그 조합에 특수 한 열거형 값을 제공 하는 것이 좋습니다 ✔️.

비트 연산은 고급 개념 이므로 간단한 작업에는 필요 하지 않습니다. <xref:System.IO.FileAccess.ReadWrite>는 이러한 특수 값의 예입니다.

❌값의 특정 조합이 유효 하지 않은 경우 플래그 열거형을 만들지 마십시오.

❌다음 지침에서 설명한 대로 값이 "모든 플래그를 지우고, 적절 하 게 이름이 지정 된 경우를 제외 하 고 플래그 열거형 값을 0으로 사용 하지 않습니다.

플래그 열거형의 값을 0으로 지정 ✔️ 합니다 `None` . 플래그 열거형의 경우 값은 항상 "모든 플래그가 지워졌습니다."을 의미 해야 합니다.

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>열거형에 값 추가

이미 제공 된 후에는 열거형에 값을 추가 해야 한다는 것을 발견 하는 것이 일반적입니다. 잘못 작성 된 응용 프로그램은 새 값을 올바르게 처리 하지 못할 수 있으므로 새로 추가 된 값이 기존 API에서 반환 될 때 응용 프로그램 호환성 문제가 발생할 수 있습니다.

약간의 호환성 위험에도 불구 하 고 열거형에 값을 추가 하는 것이 좋습니다. ✔️

열거형 추가로 인 한 응용 프로그램 호환성 문제에 대 한 실제 데이터가 있는 경우 새 값과 이전 값을 반환 하는 새 API를 추가 하 고 이전 값만 반환 하는 이전 API를 사용 중단 하는 것이 좋습니다. 이렇게 하면 기존 응용 프로그램이 호환 되는 상태로 유지 됩니다.

*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
