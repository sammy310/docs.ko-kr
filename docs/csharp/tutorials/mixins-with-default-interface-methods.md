---
title: 기본 인터페이스 메서드를 사용하여 mixin 형식 만들기
description: 기본 인터페이스 멤버를 사용하여 구현자에 대한 선택적 기본 구현으로 인터페이스를 확장할 수 있습니다.
ms.technology: csharp-advanced-concepts
ms.date: 10/04/2019
ms.openlocfilehash: 798413f0071159893de39f3e190a9b2693571bb7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039270"
---
# <a name="tutorial-mix-in-functionality-when-creating-classes-using-interfaces-with-default-interface-methods"></a>자습서: 기본 인터페이스 메서드를 사용하는 인터페이스를 통해 클래스를 만드는 경우의 기능 혼합

.NET Core 3.0의 C# 8.0에서부터, 인터페이스 멤버 선언 시 구현을 정의할 수 있습니다. 이 기능은 인터페이스에 선언된 기능에 대한 기본 구현을 정의할 수 있는 새로운 기능을 제공합니다. 클래스는 기능을 재정의할 시기, 기본 기능을 사용할 시기 및 불연속 기능에 대한 지원을 선언하지 않을 시기를 선택할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
>
> * 불연속 기능을 설명하는 구현을 사용하여 인터페이스를 만듭니다.
> * 기본 구현을 사용하는 클래스를 만듭니다.
> * 기본 구현의 일부 또는 전체를 재정의하는 클래스를 만듭니다.

## <a name="prerequisites"></a>전제 조건

C# 8.0 컴파일러를 포함하여 .NET Core를 실행하도록 머신을 설정해야 합니다. C# 8.0 컴파일러는 [Visual Studio 2019 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 또는 [.NET Core 3.0 SDK 및 이후 버전](https://dotnet.microsoft.com/download/dotnet-core)부터 사용할 수 있습니다.

## <a name="limitations-of-extension-methods"></a>확장 메서드의 제한 사항

인터페이스의 일부로 나타나는 동작을 구현할 수 있는 한 가지 방법은 기본 동작을 제공하는 [확장 메서드](../programming-guide/classes-and-structs/extension-methods.md)를 정의하는 것입니다. 인터페이스는 해당 멤버를 구현하는 클래스에 더 큰 노출 영역을 제공하는 동시에 최소 멤버 집합을 선언합니다. 예를 들어 <xref:System.Linq.Enumerable>의 확장 메서드는 모든 시퀀스가 LINQ 쿼리의 원본이 되도록 구현합니다.

확장 메서드는 선언된 변수 형식을 사용하여 컴파일 시간에 확인됩니다. 인터페이스를 구현하는 클래스는 모든 확장 메서드에 대해 더 나은 구현을 제공할 수 있습니다. 컴파일러가 해당 구현을 선택할 수 있도록 변수 선언이 구현 형식과 일치해야 합니다. 컴파일 시간 형식이 인터페이스와 일치하는 경우 메서드 호출은 확장 메서드를 확인합니다. 확장 메서드의 또 다른 문제는 확장 메서드를 포함하는 클래스에 액세스할 수 있는 모든 위치에서 메서드에 액세스할 수 있다는 것입니다. 클래스는 확장 메서드에 선언된 기능을 제공해야 하는지 제공하지 않아야 하는지 여부에 관계없이 선언할 수 없습니다.

C# 8.0부터 기본 구현을 인터페이스 메서드로 선언할 수 있습니다. 그러면 모든 클래스에서 자동으로 기본 구현을 사용합니다. 더 나은 구현을 제공할 수 있는 모든 클래스는 더 나은 알고리즘으로 인터페이스 메서드를 재정의할 수 있습니다. 어떤 의미에서 이 기술은 [확장 메서드](../programming-guide/classes-and-structs/extension-methods.md)를 사용하는 방법과 비슷합니다.

이 문서에서는 기본 인터페이스 구현에서 새 시나리오를 사용하도록 설정하는 방법을 알아봅니다.

## <a name="design-the-application"></a>애플리케이션 설계

홈 자동화 애플리케이션을 고려합니다. 집 전체에서 사용할 수 있는 다양한 광원 및 표시등이 있을 수 있습니다. 모든 광원은 켜고 끄고 현재 상태를 보고할 수 있도록 API가 지원되어야 합니다. 일부 광원 및 표시등은 다음과 같은 다른 기능을 지원할 수 있습니다.

- 광원을 켜고 타이머에 맞춰 끕니다.
- 일정 시간 동안 광원이 깜박입니다.

이러한 확장 기능 중 일부는 최소 설정을 지원하는 디바이스에서 에뮬레이트될 수 있습니다. 이는 기본 구현을 제공한다는 의미입니다. 더 많은 기능이 내장된 디바이스의 경우 디바이스 소프트웨어는 기본 기능을 사용합니다. 다른 광원의 경우 인터페이스를 구현하고 기본 구현을 사용하도록 선택할 수 있습니다.

기본 인터페이스 멤버는 이 시나리오에서 확장 메서드보다 더 나은 솔루션입니다. 클래스 작성자는 구현할 인터페이스를 제어할 수 있습니다. 선택한 인터페이스는 메서드로 사용할 수 있습니다. 또한 기본 인터페이스 메서드는 기본적으로 가상이기 때문에 메서드 디스패치는 항상 클래스에서 구현을 선택합니다. 

이러한 차이점을 보여주는 코드를 만들어 보겠습니다.

## <a name="create-interfaces"></a>인터페이스 만들기

모든 광원의 동작을 정의하는 인터페이스를 만드는 것부터 시작합니다.

[!code-csharp[Declare base interface](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetILightInterfaceV1)]

기본 오버헤드 광원 픽스쳐는 다음 코드와 같이 이 인터페이스를 구현할 수 있습니다.

[!code-csharp[First overhead light](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetOverheadLightV1)]

이 자습서에서 코드는 IoT 디바이스를 구동하지 않지만 콘솔에 메시지를 작성하여 해당 활동을 에뮬레이트합니다. 집을 자동화하지 않고 코드를 탐색할 수 있습니다.

다음으로 시간 제한 후 자동으로 꺼질 수 있는 광원의 인터페이스를 정의해 보겠습니다.

[!code-csharp[pure Timer interface](~/samples/csharp/tutorials/mixins-with-interfaces/UnusedExampleCode.cs?name=SnippetPureTimerInterface)]

기본 구현을 오버헤드 광원에 추가할 수 있지만, 이 인터페이스 정의를 수정하여 `virtual` 기본 구현을 제공하는 것이 더 좋습니다.

[!code-csharp[Timer interface](~/samples/csharp/tutorials/mixins-with-interfaces/ITimerLight.cs?name=SnippetTimerLightFinal)]

이러한 변경 사항 추가로 `OverheadLight` 클래스는 인터페이스에 대한 지원을 선언하여 타이머 함수를 구현할 수 있습니다.

```csharp
public class OverheadLight : ITimerLight { }
```

다른 광원 형식은 보다 정교한 프로토콜을 지원할 수 있습니다. 다음 코드와 같이 `TurnOnFor`에 대한 자체 구현을 제공할 수 있습니다.

[!code-csharp[Override the timer function](~/samples/csharp/tutorials/mixins-with-interfaces/HalogenLight.cs?name=SnippetHalogenLight)]

가상 클래스 메서드를 재정의하는 것과 달리 `HalogenLight` 클래스의 `TurnOnFor` 선언에는 `override` 키워드가 사용되지 않습니다. 

## <a name="mix-and-match-capabilities"></a>조합 및 일치 기능

고급 기능을 도입할수록 기본 인터페이스 방법의 장점이 더 명확해집니다. 인터페이스를 사용하면 기능을 조합하고 일치시킬 수 있습니다. 또한 각 클래스 작성자가 기본 구현과 사용자 지정 구현 중에서 선택할 수 있습니다. 깜박이는 광원에 대한 기본 구현으로 인터페이스를 추가해 보겠습니다.

[!code-csharp[Define the blinking light interface](~/samples/csharp/tutorials/mixins-with-interfaces/IBlinkingLight.cs?name=SnippetBlinkingLight)]

기본 구현을 사용하면 모든 광원이 깜박일 수 있습니다. 오버헤드 광원은 기본 구현을 사용하여 타이머 및 깜박임 기능을 모두 추가할 수 있습니다.

[!code-csharp[Use the default blink function](~/samples/csharp/tutorials/mixins-with-interfaces/OverheadLight.cs?name=SnippetOverheadLight)]

새로운 광원 형식인 `LEDLight`는 timer 함수와 blink 함수를 직접 지원합니다. 이 광원 스타일은 `ITimerLight` 및 `IBlinkingLight` 인터페이스를 모두 구현하고 `Blink` 메서드를 재정의합니다.

[!code-csharp[Override the blink function](~/samples/csharp/tutorials/mixins-with-interfaces/LEDLight.cs?name=SnippetLEDLight)]

`ExtraFancyLight`는 blink 및 timer 함수를 직접 지원할 수 있습니다.

[!code-csharp[Override the blink and timer function](~/samples/csharp/tutorials/mixins-with-interfaces/ExtraFancyLight.cs?name=SnippetExtraFancyLight)]

이전에 만든 `HalogenLight`는 깜박임을 지원하지 않습니다. 따라서 지원되는 인터페이스 목록에 `IBlinkingLight`를 추가하지 마세요.

## <a name="detect-the-light-types-using-pattern-matching"></a>패턴 일치를 사용하여 광원 형식 검색

다음으로 몇 가지 테스트 코드를 작성해 보겠습니다. C#의 [패턴 일치](../pattern-matching.md) 기능을 사용하여 지원되는 인터페이스를 검사하고 광원의 기능을 결정할 수 있습니다.  다음 메서드는 각 광원의 지원되는 기능을 연습합니다.

[!code-csharp[Test a light's capabilities](~/samples/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetTestLightFunctions)]

`Main` 메서드의 다음 코드는 각 광원 형식을 차례로 만들고 해당 광원을 테스트합니다.

[!code-csharp[Test a light's capabilities](~/samples/csharp/tutorials/mixins-with-interfaces/Program.cs?name=SnippetMainMethod)]

## <a name="how-the-compiler-determines-best-implementation"></a>컴파일러가 최선의 구현을 결정하는 방법

이 시나리오에서는 구현이 없는 기본 인터페이스를 보여 줍니다. `ILight` 인터페이스에 메서드를 추가하면 새로운 복잡성이 발생합니다. 기본 인터페이스 메서드를 제어하는 언어 규칙은 여러 파생 인터페이스를 구현하는 구체적인 클래스에 대한 영향을 최소화합니다. 새 메서드로 원래 인터페이스를 개선하여 사용 방법을 변경할 수 있는 방법을 확인해 보겠습니다. 모든 표시등 광원은 해당 전원 상태를 열거형 값으로 보고할 수 있습니다.

[!code-csharp[Enumeration for power status](~/samples/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetPowerStatus)]

기본 구현에서는 AC 전원이라고 가정합니다.

[!code-csharp[Report a default power status](~/samples/csharp/tutorials/mixins-with-interfaces/ILight.cs?name=SnippetILightInterface)]

`ExtraFancyLight`에서 `ILight` 인터페이스 및 파생된 인터페이스, `ITimerLight` 및 `IBlinkingLight`에 대한 지원을 선언하더라도 이러한 변경 내용은 완전히 컴파일됩니다. `ILight` 인터페이스에 선언된 "가장 가까운" 구현은 하나뿐입니다. 재정의를 선언한 모든 클래스는 하나의 "가장 가까운" 구현이 됩니다. 이전 클래스에서 다른 파생 인터페이스의 멤버를 재정의하는 예를 살펴보았습니다.

여러 파생 인터페이스에서 동일한 메서드를 재정의하지 마세요. 이렇게 하면 클래스가 파생된 두 인터페이스를 모두 구현할 때마다 모호한 메서드 호출을 만듭니다. 컴파일러는 더 나은 단일 메서드를 선택할 수 없으므로 오류가 발생합니다. 예를 들어 `IBlinkingLight` 및 `ITimerLight` 모두 `PowerStatus` 재정의를 구현하는 경우 `OverheadLight`는 보다 구체적인 재정의를 제공해야 합니다. 그렇지 않으면 컴파일러는 두 파생 인터페이스의 구현 사이에서 선택할 수 없습니다. 일반적으로 인터페이스 정의를 작게 유지하고 하나의 기능에 집중하여 이러한 상황을 방지할 수 있습니다. 이 시나리오에서 광원의 각 기능은 고유한 인터페이스입니다. 여러 인터페이스는 클래스에 의해서만 상속됩니다.

이 샘플은 클래스에 결합될 수 있는 불연속 기능을 정의할 수 있는 시나리오를 보여 줍니다. 클래스가 지원하는 인터페이스를 선언하여 지원되는 기능 집합을 선언합니다. 가상 기본 인터페이스 메서드를 사용하면 클래스가 일부 또는 모든 인터페이스 메서드에 대해 다른 구현을 사용하거나 정의할 수 있습니다. 이 언어 기능은 빌드 중인 실제 시스템을 모델링하는 새로운 방법을 제공합니다. 기본 인터페이스 메서드는 해당 기능의 가상 구현을 사용하여 다른 기능을 조합하고 일치시킬 수 있는 관련 클래스를 더 명확하게 표현하는 방법을 제공합니다.
