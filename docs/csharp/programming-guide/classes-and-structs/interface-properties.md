---
title: 인터페이스 속성 - C# 프로그래밍 가이드
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626622"
---
# <a name="interface-properties-c-programming-guide"></a>인터페이스 속성(C# 프로그래밍 가이드)

[interface](../../language-reference/keywords/interface.md)에 속성을 선언할 수 있습니다. 다음 예제에서는 인터페이스 속성 접근자를 선언합니다.

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

일반적으로 인터페이스 속성에는 본문이 없습니다. 접근자는 속성이 읽기/쓰기인지, 읽기 전용인지, 쓰기 전용인지를 나타냅니다. 클래스 및 구조체와 달리, 접근자를 본문 없이 선언해도 [자동 구현 속성](auto-implemented-properties.md)이 선언되지 않습니다. C# 8.0부터 인터페이스는 멤버에 대한 기본 구현(속성 포함)을 정의할 수 있습니다. 인터페이스는 인스턴스 데이터 필드를 정의할 수 없으므로 인터페이스에서 속성에 대한 기본 구현을 정의하는 것은 드문 일입니다.

## <a name="example"></a>예제

이 예제에서 `IEmployee` 인터페이스에는 읽기/쓰기 속성 `Name`과 읽기 전용 속성 `Counter`가 있습니다. `Employee` 클래스는 `IEmployee` 인터페이스를 구현하고 이러한 두 속성을 사용합니다. 프로그램은 새 직원의 이름과 현재 직원 수를 읽고 직원 이름과 계산된 직원 수를 표시합니다.

멤버가 선언된 인터페이스를 참조하는 속성의 정규화된 이름을 사용할 수 있습니다. 예를 들어:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

앞의 예제에서는 [명시적 인터페이스 구현](../interfaces/explicit-interface-implementation.md)을 보여 주었습니다. 예를 들어 `Employee` 클래스가 두 인터페이스 `ICitizen` 및 `IEmployee`를 구현하고 두 인터페이스에 모두 `Name` 속성이 있으면 명시적 인터페이스 멤버 구현이 필요합니다. 즉, 다음과 같은 속성 선언이 있다고 가정합니다.

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

이 선언은 `IEmployee` 인터페이스의 `Name` 속성을 구현합니다. 또한 다음과 같은 선언이 있다고 가정합니다.

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

이 선언은 `ICitizen` 인터페이스의 `Name` 속성을 구현합니다.

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>샘플 출력

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [속성](./properties.md)
- [속성 사용](./using-properties.md)
- [속성 및 인덱서 비교](../indexers/comparison-between-properties-and-indexers.md)
- [인덱서](../indexers/index.md)
- [인터페이스](../interfaces/index.md)
