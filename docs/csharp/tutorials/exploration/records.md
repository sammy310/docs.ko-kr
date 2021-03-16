---
title: 레코드 형식 사용 - C# 자습서
description: 레코드 종류를 사용하는 방법, 레코드의 계층 구조를 작성하는 방법, 클래스에 대해 레코드를 선택하는 시기에 대해 알아봅니다.
ms.date: 11/12/2020
ms.openlocfilehash: 33075c4cafc9a91683960daa8101c9f1defaa36a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258958"
---
# <a name="create-record-types"></a>레코드 종류 만들기

C# 9에서는 클래스나 구조체 대신 만들 수 있는 새 참조 형식인 ‘레코드’를 소개합니다. 레코드는 레코드 종류가 ‘값 기반 같음’을 사용한다는 점에서 클래스와 구분됩니다. 레코드 종류의 두 변수는 레코드 종류 정의가 동일한 경우와 모든 필드에 대해 두 레코드의 값이 같은 경우에 같습니다. 클래스 형식의 두 변수는 참조되는 개체가 동일한 클래스 형식이고 변수가 동일한 개체를 참조하는 경우에 같습니다. 값 기반 같음은 레코드 종류에 필요할 수 있는 다른 기능을 의미합니다. 컴파일러는 `class`대신 `record`를 선언할 때 이러한 멤버 대부분을 생성합니다.

이 자습서에서 학습할 방법은 다음과 같습니다.

> [!div class="checklist"]
>
> - `class`를 선언할지 `record`를 선언할지를 결정합니다.
> - 레코드 종류 및 위치 레코드 종류를 선언합니다.
> - 레코드에서 컴파일러 생성 메서드를 자신의 메서드로 대체합니다.

## <a name="prerequisites"></a>사전 요구 사항

C# 9.0 이상 컴파일러를 포함하여 .NET 5 이상을 실행하도록 컴퓨터를 설정해야 합니다. C# 9.0 컴파일러는 [Visual Studio 2019 버전 16.8](https://visualstudio.microsoft.com/vs) 또는 [.NET 5.0 SDK](https://dotnet.microsoft.com/download)부터 사용할 수 있습니다.

## <a name="characteristics-of-records"></a>레코드의 특징

`class` 또는 `struct` 키워드 대신 `record` 키워드로 형식을 선언하여 ‘레코드’를 정의합니다. 레코드는 참조 형식이며 값 기반 같음 의미 체계를 따릅니다. 값 의미 체계를 적용하기 위해 컴파일러는 레코드 종류에 대해 여러 가지 메서드를 생성합니다.

- <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>의 재정의.
- 매개 변수가 레코드 종류인 가상 `Equals` 메서드.
- <xref:System.Object.GetHashCode?displayProperty=nameWithType>의 재정의.
- `operator ==` 및 `operator !=`에 대한 메서드.
- 레코드 종류는 <xref:System.IEquatable%601?displayProperty=nameWithType>를 구현.

또한 레코드는 <xref:System.Object.ToString?displayProperty=nameWithType>의 재정의를 제공합니다. 컴파일러는 <xref:System.Object.ToString?displayProperty=nameWithType>을 사용하여 레코드를 표시하기 위해 메서드를 합성합니다. 이 자습서에 대한 코드를 작성할 때 이러한 멤버를 살펴봅니다. 레코드는 레코드의 비파괴적 변경을 사용하도록 설정하는 `with` 식을 지원합니다.

더욱 간결한 구문을 사용하여 ‘위치 레코드’를 선언할 수도 있습니다. 컴파일러는 위치 레코드를 선언할 때 더 많은 메서드를 합성합니다.

- 매개 변수가 레코드 선언의 위치 매개 변수와 일치하는 기본 생성자.
- 기본 생성자의 각 매개 변수에 대한 퍼블릭 init 전용 속성.
- 레코드에서 속성을 추출하는 `Deconstruct` 메서드.

## <a name="build-temperature-data"></a>온도 데이터 빌드

데이터 및 통계는 레코드를 사용하려는 시나리오 중 하나입니다. 이 자습서에서는 서로 다른 용도로 ‘도일’(degree days)을 계산하는 애플리케이션을 빌드합니다. ‘도일’은 일정 기간(일, 주, 월) 동안 열(또는 열 부족)을 측정한 값입니다. 도일은 에너지 사용량을 추적하고 예측합니다. 더운 날이 많을수록 에어컨 사용량이 많아지고, 추운 날이 많을수록 난로 사용량이 많아집니다. 도일은 식물 개체군 관리에 도움이 됩니다. 도일은 계절 변화에 따른 식물 성장과 상관 관계가 있습니다. 도일은 기후에 따라 이동하는 동물 종의 이동을 추적하는 데 도움이 됩니다.

수식은 지정된 날짜의 평균 온도와 기준 온도를 기반으로 합니다. 시간에 따른 도일을 계산하려면 일정 기간 동안 각 날짜의 높은 온도와 낮은 온도가 필요합니다. 먼저 새 애플리케이션을 만들어 보겠습니다. 새 콘솔 애플리케이션을 만듭니다. “DailyTemperature.cs”라는 새 파일에 새 레코드 종류를 만듭니다.

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DailyRecord":::

위의 코드는 ‘위치 레코드’를 정의합니다. `HighTemp`와 `LowTemp`의 두 속성을 포함하는 참조 형식을 만들었습니다. 이러한 속성은 ‘init 전용 속성’이므로 생성자에서 설정하거나 속성 이니셜라이저를 사용하여 설정할 수 있습니다. `DailyTemperature` 형식에는 두 개의 속성과 일치하는 두 개의 매개 변수가 있는 ‘기본 생성자’도 있습니다. 기본 생성자를 사용하여 `DailyTemperature` 레코드를 초기화합니다.

:::code language="csharp" source="snippets/record-types/Program.cs" ID="DeclareData":::

위치 레코드를 포함하여 고유한 속성 또는 메서드를 레코드에 추가할 수 있습니다. 각 날짜의 평균 온도를 계산해야 합니다. `DailyTemperature` 레코드에 해당 속성을 추가할 수 있습니다.

:::code language="csharp" source="snippets/record-types/DailyTemperature.cs" ID="TemperatureRecord":::

이 데이터를 사용할 수 있는지 확인해 보겠습니다. `Main` 메서드에 다음 코드를 추가합니다.

```csharp
foreach (var item in data)
    Console.WriteLine(item);
```

애플리케이션을 실행하면 다음과 같은 출력이 표시됩니다(공간상의 이유로 여러 행을 제거함).

```dotnetcli
DailyTemperature { HighTemp = 57, LowTemp = 30, Mean = 43.5 }
DailyTemperature { HighTemp = 60, LowTemp = 35, Mean = 47.5 }


DailyTemperature { HighTemp = 80, LowTemp = 60, Mean = 70 }
DailyTemperature { HighTemp = 85, LowTemp = 66, Mean = 75.5 }
```

위의 코드는 컴파일러에 의해 합성된 `ToString` 재정의의 출력을 보여 줍니다. 다른 텍스트를 원하는 경우 `ToString`의 고유한 버전을 작성할 수 있습니다. 그러면 컴파일러에서 자동으로 버전을 합성할 수 없습니다.

## <a name="compute-degree-days"></a>도일 계산

도일을 계산하려면 지정된 날짜의 기준 온도와 평균 온도의 차이를 계산합니다. 시간에 따른 더위를 측정하려면 평균 온도가 기준보다 낮은 날짜를 모두 삭제합니다. 시간에 따른 추위를 측정하려면 평균 온도가 기준보다 높은 날짜를 모두 삭제합니다. 예를 들어 미국은 난방 및 냉방 도일의 기준으로 65F를 사용합니다. 이 온도는 난방 또는 냉방이 필요하지 않은 온도입니다. 하루 평균 온도가 70F인 경우 그날 냉방 도일은 5이고 난방 도일은 0입니다. 반대로 평균 온도가 55F인 경우 난방 도일은 10이고 냉방 도일은 0입니다.

이러한 수식을 레코드 형식의 작은 계층 구조, 즉 하나의 추상적 도일 형식과 그 아래에 난방 도일 및 냉방 도일이라는 구체적인 두 가지 형식으로 표현할 수 있습니다. 이러한 형식은 위치 레코드일 수도 있습니다. 기준 온도와 일련의 일일 온도를 기본 생성자의 인수로 사용합니다.

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DegreeDaysRecords":::

추상 `DegreeDays` 레코드는 `HeatingDegreeDays` 및 `CoolingDegreeDays` 레코드의 공유 기본 클래스입니다. 파생 레코드의 기본 생성자 선언에서는 기본 레코드 초기화를 관리하는 방법을 보여 줍니다. 파생 레코드는 기본 레코드 기본 생성자의 모든 매개 변수에 대한 매개 변수를 선언합니다. 기본 레코드는 이러한 속성을 선언하고 초기화합니다. 파생 레코드는 이러한 속성을 숨기지는 않지만 기본 레코드에 선언되지 않은 매개 변수의 속성만 만들고 초기화합니다. 이 예제에서 파생 레코드는 새로운 기본 생성자 매개 변수를 추가하지 않습니다. `Main` 메서드에 다음 코드를 추가하여 코드를 테스트합니다.

:::code language="csharp" source="snippets/record-types/Program.cs" ID="HeatingAndCooling":::

다음과 같은 출력이 표시됩니다.

```dotnetcli
HeatingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 85 }
CoolingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 71.5 }
```

## <a name="define-compiler-synthesized-methods"></a>컴파일러 합성 메서드 정의

코드는 해당 기간 동안의 정확한 난방 및 냉방 도일 수를 계산합니다. 그러나 이 예제에서는 레코드에 대한 합성 메서드 중 일부를 바꿔야 하는 이유를 보여 줍니다. clone 메서드를 제외하고 고유한 버전의 컴파일러 합성 메서드를 레코드 종류에서 선언할 수 있습니다. clone 메서드는 컴파일러 생성 이름을 사용하므로 다른 구현을 제공할 수 없습니다. 이러한 합성 메서드로는 복사 생성자, <xref:System.IEquatable%601?displayProperty=nameWithType> 인터페이스의 멤버, 같음 및 같지 않음 테스트, <xref:System.Object.GetHashCode>가 있습니다. 이러한 용도로 `PrintMembers`를 합성합니다. 고유한 `ToString`을 선언할 수도 있지만 `PrintMembers`는 상속 시나리오에 더 나은 옵션을 제공합니다. 고유한 버전의 합성 메서드를 제공하려면 서명이 합성 메서드와 일치해야 합니다.

콘솔 출력의 `TempRecords` 요소는 유용하지 않습니다. 이 요소는 형식만 표시하고 다른 항목은 전혀 표시하지 않습니다. 합성 `PrintMembers` 메서드의 고유한 구현을 제공하여 이 동작을 변경할 수 있습니다. 서명은 `record` 선언에 적용된 한정자에 따라 달라집니다.

- 레코드 종류가 `sealed`이면 서명은 `private bool PrintMembers(StringBuilder builder);`입니다.
- 레코드 종류가 `sealed`가 아니고 `object`에서 파생되면(즉, 기본 레코드를 선언하지 않음) 서명은 `protected virtual bool PrintMembers(StringBuilder builder);`입니다.
- 레코드 종류가 `sealed`가 아니고 다른 레코드에서 파생되면 서명은 `protected override bool PrintMembers(StringBuilder builder);`입니다.

이러한 규칙은 `PrintMembers`의 용도에 대한 이해를 통해 가장 쉽게 이해할 수 있습니다. `PrintMembers`는 레코드 종류의 각 속성에 대한 정보를 문자열에 추가합니다. 계약에서는 표시할 멤버를 추가하려면 기본 레코드가 필요하며 파생 멤버는 해당 멤버를 추가하는 것으로 가정합니다. 각 레코드 종류는 `HeatingDegreeDays`에 대한 다음 예제와 유사하게 표시되는 `ToString` 재정의를 합성합니다.

```csharp
public override string ToString()
{
    StringBuilder stringBuilder = new StringBuilder();
    stringBuilder.Append("HeatingDegreeDays");
    stringBuilder.Append(" { ");
    if (PrintMembers(stringBuilder))
    {
        stringBuilder.Append(" ");
    }
    stringBuilder.Append("}");
    return stringBuilder.ToString();
}
```

컬렉션의 형식을 출력하지 않는 `DegreeDays` 레코드에 `PrintMembers` 메서드를 선언합니다.

:::code language="csharp" source="snippets/record-types/DegreeDays.cs" ID="AddPrintMembers":::

서명은 컴파일러의 버전과 일치하도록 `virtual protected` 메서드를 선언합니다. 잘못된 접근자를 가져와도 걱정할 필요가 없습니다. 언어에서 올바른 서명을 적용합니다. 합성 메서드에 대한 올바른 한정자를 잊은 경우 컴파일러는 올바른 서명을 가져오는 데 도움이 되는 경고 또는 오류를 발생시킵니다.

## <a name="non-destructive-mutation"></a>비파괴적 변경

위치 레코드의 합성 멤버는 레코드의 상태를 수정하지 않습니다. 목표는 변경이 불가능한 레코드를 더욱 쉽게 만들 수 있도록 하는 것입니다. `HeatingDegreeDays` 및 `CoolingDegreeDays`에 대한 위의 선언을 다시 살펴보세요. 추가된 멤버는 레코드의 값에 대해 계산을 수행하지만 상태를 변경하지는 않습니다. 위치 레코드를 사용하면 변경이 불가능한 참조 형식을 더욱 쉽게 만들 수 있습니다.

변경이 불가능한 참조 형식을 만드는 것은 비파괴적 변경을 사용한다는 의미입니다. [`with` 식](../../language-reference/operators/with-expression.md)을 사용하여 기존 레코드 인스턴스와 유사한 새 레코드 인스턴스를 만듭니다. 이러한 식은 복사본을 수정하는 추가 할당이 있는 복사본 생성입니다. 그러면 각 속성이 기존 레코드에서 복사되고 선택적으로 수정된 새 레코드 인스턴스가 생성됩니다. 원래 레코드는 변경되지 않습니다.

`with` 식을 보여 주는 몇 가지 기능을 프로그램에 추가해 보겠습니다. 먼저 동일한 데이터를 사용하여 증가하는 도일을 계산하는 새 레코드를 만들어 보겠습니다. 일반적으로 ‘증가하는 도일’은 41F를 기준으로 사용하고 기준보다 높은 온도를 측정합니다. 동일한 데이터를 사용하려면 `coolingDegreeDays`와 유사하지만 기본 온도는 다른 새 레코드를 만들 수 있습니다.

:::code language="csharp" source="snippets/record-types/Program.cs" ID="GrowingDegreeDays":::

계산된 도수를 더 높은 기준 온도로 생성된 수와 비교할 수 있습니다. 레코드는 ‘참조 형식’이며 이러한 복사본은 단순 복사본입니다. 데이터의 배열은 복사되지 않지만 두 레코드 모두 동일한 데이터를 참조합니다. 이러한 사실은 또 다른 시나리오에서 장점이 됩니다. 증가하는 도일의 경우 이전 5일간의 합계를 추적하는 것이 유용합니다. `with` 식을 사용하여 다른 소스 데이터로 새 레코드를 만들 수 있습니다. 다음 코드에서는 이러한 누적의 컬렉션을 빌드하고 값을 표시합니다.

:::code language="csharp" source="snippets/record-types/Program.cs" ID="RunningFiveDayTotal":::

`with` 식을 사용하여 레코드 복사본을 만들 수도 있습니다. `with` 식의 중괄호 사이에 속성을 지정하지 마세요. 그러면 복사본을 만들고 속성은 변경하지 않습니다.

```csharp
var growingDegreeDaysCopy = growingDegreeDays with { };
```

완성된 애플리케이션을 실행하여 결과를 확인합니다.

## <a name="summary"></a>요약

이 자습서에서는 레코드의 여러 측면을 보여 주었습니다. 레코드는 기본 용도가 데이터 저장인 참조 형식에 대해 간결한 구문을 제공합니다. 개체 지향 클래스의 기본 용도는 책임을 정의하는 것입니다. 이 자습서에서는 간결한 구문을 사용하여 레코드에 대한 init 전용 속성을 선언할 수 있는 ‘위치 레코드’를 집중적으로 살펴보았습니다. 컴파일러는 레코드를 복사하고 비교하기 위해 레코드의 여러 멤버를 합성합니다. 레코드 종류에 필요한 다른 멤버를 추가할 수 있습니다. 컴파일러 생성 멤버는 상태가 변경되지 않는다는 점을 이해하고 변경 불가능한 레코드 형식을 만들 수 있습니다. 그리고 `with` 식을 사용하여 비파괴적 변경을 쉽게 지원할 수 있습니다.

레코드는 형식을 정의하는 또 다른 방법을 추가합니다. `class` 정의를 사용하여 개체의 책임이나 동작에 중점을 둔 개체 지향 계층 구조를 만듭니다. 데이터를 저장할 뿐만 아니라 아주 작아서 효율적으로 복사할 수 있는 데이터 구조에 대해 `struct` 형식을 만듭니다. 값 기반 같음 및 비교를 원하지만 값을 복사하지 않고 참조 변수를 사용하려는 경우 레코드를 만듭니다.

[레코드 형식에 대한 C# 언어 참조 설명서](../../language-reference/builtin-types/record.md) 및 [제안된 레코드 형식 사양](~/_csharplang/proposals/csharp-9.0/records.md)을 참조하여 레코드에 대한 자세한 설명을 확인할 수 있습니다.
