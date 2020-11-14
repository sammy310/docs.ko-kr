---
title: 개체에서 패턴 사용 - C# 자습서
description: 이 자습서에서는 클래스 멤버에서 패턴 일치를 사용하여 개체 동작에 보다 좋은 모델을 만드는 방법을 배웁니다.
ms.date: 11/05/2020
ms.openlocfilehash: 072f6f57696504c2d691473e3a43c1cda53f227f
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "94332178"
---
# <a name="use-pattern-matching-to-build-your-class-behavior-for-better-code"></a>패턴 일치를 사용하여 코드를 개선하는 클래스 동작 빌드

C#의 패턴 일치 기능은 알고리즘을 표현하는 구문을 제공합니다. 이러한 방법을 사용하여 클래스에서 동작을 구현할 수 있습니다. 개체 지향 클래스 디자인을 데이터 지향 구현과 결합하면 실제 개체를 모델링하면서 간결한 코드를 제공할 수 있습니다.

이 자습서에서 학습할 방법은 다음과 같습니다.

> [!div class="checklist"]
>
> - 데이터 패턴을 사용하여 개체 지향 클래스를 표현합니다.
> - C#의 패턴 일치 기능을 사용하여 이러한 패턴을 구현합니다.
> - 컴파일러 진단을 활용하여 구현의 유효성을 검사합니다.

## <a name="prerequisites"></a>필수 구성 요소

C# 9.0 컴파일러를 포함하여 .NET 5를 실행하도록 컴퓨터를 설정해야 합니다. C# 9.0 컴파일러는 [Visual Studio 2019 버전 16.8 미리 보기](https://visualstudio.microsoft.com/vs/preview/) 또는 [.NET 5.0 SDK 미리 보기](https://dotnet.microsoft.com/download/dotnet/5.0)부터 사용할 수 있습니다.

## <a name="build-a-simulation-of-a-canal-lock"></a>운하 갑문 시뮬레이션 빌드

이 자습서에서는 [운하 갑문](https://en.wikipedia.org/wiki/Lock_(water_navigation))을 시뮬레이트하는 C# 클래스를 빌드합니다. 간단히 말해 운하 갑문은 서로 수위가 다른 두 수역 간을 이동하는 배들을 올리고 내리는 장치입니다. 갑문에는 두 개의 수문과 수위를 변경하는 몇 가지 메커니즘이 있습니다.

정상 작동 시 배는 갑문 안의 수위와 배가 진입하는 쪽의 수위가 일치할 때 두 개의 수문 중 하나로 들어옵니다. 갑문 안에 들어오면 배가 갑문에서 나가는 쪽의 수위와 일치하도록 갑문 안 수위가 변경됩니다. 수위가 이쪽 수위와 일치하면 출구 쪽 수문이 열립니다. 조작자가 운하에서 위험한 상황을 초래하지 않도록 안전 조치가 마련되어 있습니다. 두 수문을 모두 닫은 경우에만 수위를 변경할 수 있습니다. 하나의 수문만 열려 있을 수 있습니다. 수문을 열려면 갑문 내 수위가 열려는 수문 밖의 수위와 일치해야 합니다.

이 동작을 C# 클래스를 빌드하여 모델링할 수 있습니다. `CanalLock` 클래스는 두 수문을 열거나 닫는 명령을 지원합니다. 수위를 높이거나 낮추는 다른 명령도 클래스에 포함됩니다. 클래스는 양쪽 수문의 현재 상태와 수위를 읽는 속성도 지원해야 합니다. 메서드는 안전 조치를 구현합니다.

## <a name="define-a-class"></a>클래스 정의

`CanalLock` 클래스를 테스트하는 콘솔 애플리케이션을 빌드합니다. Visual Studio 또는 .NET CLI를 사용하여 .NET 5용 콘솔 프로젝트를 새로 만듭니다. 그런 다음 새 클래스를 추가하고 이름을 `CanalLock`으로 지정합니다. 다음으로 공용 API를 디자인하되 메서드는 구현하지 않은 상태로 둡니다.

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="APIDesign":::

앞의 코드는 개체를 초기화하므로 두 수문이 모두 닫혀 있고 수위는 낮습니다. 그런 다음 클래스의 첫 번째 구현을 만들 때 지침이 될 다음 테스트 코드를 `Main` 메서드에 작성합니다.

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HappyTests":::

다음으로 `CanalLock` 클래스에서 각 메서드의 첫 번째 구현을 추가합니다. 다음 코드는 안전 규칙을 고려하지 않고 클래스의 메서드를 구현합니다. 안전 테스트는 나중에 추가합니다.

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="FirstImplementation":::

지금까지 작성한 테스트는 통과됩니다. 기초를 구현했습니다. 이제 첫 번째 실패 조건에 대한 테스트를 작성합니다. 이전 테스트의 끝에서는 두 수문이 모두 닫혀 있고 수위가 낮음으로 설정되었습니다. 상류 수문을 열려고 시도하는 테스트를 추가합니다.

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HighGateSafetyTest":::

수문이 열리기 때문에 이 테스트는 실패합니다. 첫 번째 구현으로 다음 코드를 사용하여 이를 해결할 수 있습니다.

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="SecondImplementation":::

테스트에 통과됩니다. 하지만 더 많은 테스트를 추가함에 따라 점점 더 많은 `if` 절을 추가하고 여러 속성을 테스트하게 됩니다. 추가하는 조건이 많아지면 이러한 메서드는 금방 너무 복잡해집니다.

## <a name="implement-the-commands-with-patterns"></a>패턴을 사용하여 명령 구현

더 나은 방법은 패턴을 사용하여 개체가 명령을 실행하기에 유효한 상태에 있는지 확인하는 것입니다. 명령이 세 변수(수문 상태, 수위, 새 설정)의 함수로 허용되는지 여부를 표현할 수 있습니다.

| 새 설정 | 수문 상태 | 수위 | 결과             |
| ----------- | ---------- | ----------- | ------------------ |
| 종결      | 종결     | 높은        | 종결             |
| 종결      | 종결     | 낮음         | 종결             |
| 종결      | 열기       | 높은        | 열기               |
| ~~해결됨~~  | ~~열기~~   | ~~낮음~~     | ~~해결됨~~         |
| 열기        | 해결됨     | 높은        | 열기               |
| 열기        | 해결됨     | 낮음         | 닫힘(오류)     |
| 열기        | 열기       | 높은        | 열기               |
| ~~열기~~    | ~~열기~~   | ~~낮음~~     | ~~닫힘(오류)~~ |

테이블의 네 번째 및 마지막 행은 잘못되었기 때문에 텍스트에 취소선이 사용됩니다. 이제 추가할 코드는 수위가 낮을 때 상류 수문이 절대 열리지 않도록 해야 합니다.  이러한 상태는 단일 switch 식으로 코딩할 수 있습니다(`false`가 "닫힘"을 나타냄을 명심하세요).

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="ThirdImplementation":::

이 버전을 시험해 보세요. 테스트가 통과되며 코드의 유효성이 검사됩니다. 전체 테이블은 입력과 결과의 가능한 조합을 보여 줍니다. 즉, 개발자는 테이블을 빠르게 살펴보고 가능한 모든 입력이 포함된 것을 확인할 수 있습니다. 컴파일러를 사용하면 훨씬 더 쉬워집니다. 이전 코드를 추가한 후 컴파일러가 다음과 같은 경고를 생성하는 것을 볼 수 있습니다. *CS8524* 는 switch 식에 가능한 모든 입력이 포함되지 않음을 나타냅니다. 이 경고가 발생하는 이유는 입력 중 하나가 `enum` 형식이기 때문입니다. 컴파일러는 "가능한 모든 입력"을 기본 형식(일반적으로 `int`)의 모든 입력으로 해석합니다. 이 `switch` 식은 `enum`에서 선언된 값만 검사합니다. 경고를 제거하려면 식의 마지막 암(arm)에 대해 catch-all 무시 패턴을 추가하면 됩니다. 이 조건은 잘못된 입력을 나타내므로 예외를 throw합니다.

```csharp
_  => throw new InvalidOperationException("Invalid internal state"),
```

위의 switch arm은 모든 입력과 일치하므로 `switch` 식에서 마지막에 와야 합니다. 앞 순서로 옮겨 실험해 보세요. 그러면 패턴의 연결할 수 없는 코드를 나타내는 컴파일러 오류 *CS8510* 이 발생합니다.  switch 식의 자연적 구조를 사용하면 컴파일러가 가능한 실수에 대한 오류 및 경고를 생성할 수 있습니다. "safety net" 컴파일러를 사용하면 더 적은 반복으로 올바른 코드를 보다 쉽게 만들 수 있으며, switch arm을 와일드카드와 조합할 수 있습니다. 컴파일러는 조합으로 인해 예상하지 못한 연결 불가능한 arm이 발생하는 경우 오류를 생성하고, 필요하지 않은 arm을 제거하는 경우 경고를 생성합니다.

첫 번째 변경은 명령이 수문 닫기인 모든 arm을 결합하는 것입니다. 이는 항상 허용됩니다. switch 식의 첫 번째 arm으로 다음 코드를 추가합니다.

```csharp
(false, _, _) => false,
```

이전 switch arm을 추가한 후 명령이 `false`인 각 arm에 하나씩 4개의 컴파일러 오류가 발생합니다. 이러한 arm은 새로 추가된 arm에 이미 포함되어 있습니다. 이 네 줄은 안전하게 제거할 수 있습니다. 이 새로운 switch arm은 이 조건을 대체하기 위한 것입니다.

다음으로 명령이 수문 열기인 네 개의 arm을 단순화할 수 있습니다. 수위가 높은 두 경우 모두 수문을 열 수 있습니다. (한 경우에는 수문이 이미 열려 있습니다.) 수위가 낮은 한 경우는 예외를 throw하고 다른 경우는 발생하면 안 됩니다. 갑문이 이미 잘못된 상태인 경우 동일한 예외를 안전하게 throw해야 합니다. 이러한 arm에 대해 다음과 같은 단순화를 만들 수 있습니다.

```csharp
(true, _, WaterLevel.High) => true,
(true, false, WaterLevel.Low) => throw new InvalidOperationException("Cannot open high gate when the water is low"),
_ => throw new InvalidOperationException("Invalid internal state"),
```

테스트를 다시 실행하면 통과됩니다. `SetHighGate` 메서드의 최종 버전은 다음과 같습니다.

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalImplementaton":::

## <a name="implement-patterns-yourself"></a>직접 패턴 구현

방법을 살펴보았으므로 이제 `SetLowGate` 및 `SetWaterLevel` 메서드를 직접 입력합니다.  먼저 다음 코드를 추가하여 이러한 메서드에 대한 잘못된 작업을 테스트합니다.

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="FinalTestCode":::

애플리케이션을 다시 실행합니다. 새 테스트가 실패하는 것을 볼 수 있고, 운하 갑문이 잘못된 상태가 됩니다. 나머지 메서드를 직접 구현해 보세요. 하류 수문을 설정하는 메서드는 상류 수문을 설정하는 메서드와 비슷해야 합니다. 수위를 변경하는 메서드에 포함된 검사는 서로 다르지만 비슷한 구조를 따라야 합니다. 수위를 설정하는 메서드에 동일한 프로세스를 사용하는 것이 유용할 수 있습니다. 다음 네 개의 입력 모두로 시작합니다. 양쪽 수문의 상태, 수위의 현재 상태, 요청된 새 수위. switch 식은 다음으로 시작해야 합니다.

```csharp
CanalLockWaterLevel = (newLevel, CanalLockWaterLevel, LowWaterGateOpen, HighWaterGateOpen) switch
{
    // elided
};
```

입력할 switch arm은 총 16개입니다. 그런 다음 테스트하고 단순화합니다.

만든 메서드가 다음과 비슷합니까?

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalExercise":::

테스트에 통과되어야 하며, 운하 갑문이 안전하게 작동해야 합니다.

## <a name="summary"></a>요약

이 자습서에서는 개체의 내부 상태에 변경 내용을 적용하기 전에 패턴 일치를 사용하여 해당 상태를 확인하는 방법을 배웠습니다. 속성의 조합을 검사할 수 있습니다. 이러한 전환을 위한 테이블을 빌드한 후 코드를 테스트한 다음 가독성 및 유지 관리를 위해 단순화하세요. 이러한 초기 리팩터링은 내부 상태의 유효성을 검사하거나 다른 API 변경을 관리하는 추가 리팩터링을 시사할 수 있습니다. 이 자습서에서는 클래스와 개체를 더 많은 데이터 지향 및 패턴 기반 접근 방식과 결합하여 이러한 클래스를 구현했습니다.
