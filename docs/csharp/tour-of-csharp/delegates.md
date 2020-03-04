---
title: C# 대리자 - C# 언어 둘러보기
description: C# 대리자를 사용한 런타임에 바인딩 알아보기
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159171"
---
# <a name="delegates"></a>대리자

***대리자***는 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다. 대리자는 메서드를 변수에 할당되고 매개 변수로 전달될 수 있는 엔터티로 취급할 수 있도록 합니다. 대리자는 다른 언어의 함수 포인터와 개념이 비슷하지만 함수 포인터와 달리 대리자는 개체 지향적이며 형식이 안전한 방식입니다.

다음 예제에서는 `Function`라는 대리자 형식을 선언하고 사용합니다.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

`Function` 대리자 형식의 인스턴스는 `double` 인수를 사용하고 `double` 값을 반환하는 메서드를 참조할 수 있습니다. `Apply` 메서드는 `double[]`의 요소에 지정된 함수를 적용하여 결과가 있는 `double[]`을 반환합니다. `Main` 메서드에서 `Apply`는 세 가지 다른 함수를 `double[]`에 적용하는 데 사용됩니다.

대리자는 정적 메서드(예: 이전 예제의 `Square` 또는 `Math.Sin`) 또는 인스턴스 메서드(예: 이전 예제의 `m.Multiply`)를 참조할 수 있습니다. 인스턴스 메서드를 참조하는 대리자는 특정 개체도 참조하며, 인스턴스 메서드가 대리자를 통해 호출되는 경우 해당 개체도 이 호출에서 `this`가 됩니다.

선언 즉시 만들어지는 “인라인 메서드”인 익명 함수를 사용하여 대리자를 만들 수도 있습니다. 익명 함수는 주변 메서드의 지역 변수를 볼 수 있습니다. 다음 예제에서는 클래스를 만들지 않습니다.

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

대리자는 해당 대리자가 참조하는 메서드의 클래스를 알지 못하고 클래스가 무엇인지에 관계없이 작동합니다. 중요한 것은 참조되는 메서드가 대리자와 동일한 매개 변수와 반환 형식을 갖는다는 사실입니다.

>[!div class="step-by-step"]
>[이전](interfaces.md)
>[다음](attributes.md)
