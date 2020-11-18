---
title: 클래스와 구조체 간의 선택
description: 형식을 클래스로 디자인 하거나 형식을 구조체로 디자인 하는지 여부를 결정 하는 방법에 대해 알아봅니다. .NET에서 참조 형식 및 값 형식이 어떻게 다른 지 이해 합니다.
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
ms.openlocfilehash: b1f3d36f4a9b6e44451a8534ca79fb674071a955
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821478"
---
# <a name="choosing-between-class-and-struct"></a>클래스와 구조체 간의 선택
모든 프레임 워크 디자이너에 대 한 기본 설계 결정 사항 중 하나는 형식을 클래스 (참조 형식)로 디자인할 것인지 아니면 구조체 (값 형식)로 디자인할 것인지를 결정 하는 것입니다. 참조 형식 및 값 형식의 동작의 차이점을 이해 하는 것은이를 선택 하는 데 매우 중요 합니다.

 참조 형식 및 값 형식 간의 첫 번째 차이점은 참조 형식이 힙에 할당 되 고 가비지 수집 된다는 것입니다. 반면 값 형식은 스택에 할당 되 고 가비지 수집 됩니다. 반면에 값 형식은 스택에 할당 되거나 포함 하는 형식에서 인라인으로 할당 되며, 스택이 해제 되거나 포함 하는 형식이 할당 취소 될 때 할당 취소 됩니다. 따라서 값 형식의 할당 및 할당 취소는 참조 형식의 할당 및 할당 취소 보다 일반적으로 비용이 저렴 합니다.

 다음으로 참조 형식의 배열이 아웃오브 라인으로 할당 됩니다. 즉, 배열 요소는 힙에 있는 참조 형식의 인스턴스를 참조 하는 것입니다. 값 형식 배열은 인라인으로 할당 됩니다. 즉, 배열 요소는 값 형식의 실제 인스턴스입니다. 따라서 값 형식 배열의 할당 및 할당 취소는 참조 형식 배열의 할당 및 할당 취소 보다 훨씬 저렴 합니다. 또한 대부분의 경우 값 형식 배열은 참조 집약성이 훨씬 더 낫습니다.

 다음 차이점은 메모리 사용량과 관련이 있습니다. 값 형식은 참조 형식 또는 구현 하는 인터페이스 중 하나로 캐스팅 될 때 boxed를 가져옵니다. 값 형식으로 다시 캐스팅 될 때 unboxed가 발생 합니다. 상자는 힙에 할당 되 고 가비지 수집 되는 개체 이기 때문에 너무 많은 boxing 및 unboxing은 힙, 가비지 수집기 및 궁극적으로 응용 프로그램의 성능에 부정적인 영향을 미칠 수 있습니다.  이와 대조적으로 참조 형식이 캐스팅 될 때 이러한 boxing이 발생 하지 않습니다. 자세한 내용은 [Boxing 및 Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)을 참조 하세요.

 다음으로 참조 형식 할당은 참조를 복사 하는 반면 값 형식 할당은 전체 값을 복사 합니다. 따라서 대량 참조 형식의 할당은 대량 값 형식의 할당 보다 저렴 합니다.

 마지막으로 참조 형식은 참조로 전달 되는 반면 값 형식은 값으로 전달 됩니다. 참조 형식의 인스턴스를 변경 하면 인스턴스를 가리키는 모든 참조에 영향을 줍니다. 값 형식 인스턴스는 값으로 전달 될 때 복사 됩니다. 값 형식의 인스턴스를 변경 하는 경우 해당 복사본에 영향을 주지 않습니다. 복사본이 사용자에 의해 명시적으로 생성 되지 않지만 인수가 전달 되거나 반환 값이 반환 될 때 암시적으로 만들어지므로 변경할 수 있는 값 형식은 여러 사용자에 게 혼란을 수 있습니다. 따라서 값 형식은 변경할 수 없습니다.

 일반적으로 프레임 워크에서 대부분의 형식은 클래스 여야 합니다. 그러나 값 형식의 특성으로 인해 구조체를 사용 하는 것이 더 적합 한 경우도 있습니다.

 형식의 인스턴스가 작고 일반적으로 수명이 짧고 다른 개체에 일반적으로 포함 되는 경우 클래스 대신 구조체를 정의 하는 것이 좋습니다. ✔️

 ❌ 형식에 다음과 같은 특징이 모두 없는 경우에는 구조체를 정의 하지 마십시오.

- 이는 기본 형식 (, 등)과 비슷한 단일 값을 논리적으로 나타냅니다. `int` `double`

- 인스턴스 크기는 16 바이트 미만입니다.

- 변경할 수 없습니다.

- 자주 boxing 하지 않아도 됩니다.

 다른 모든 경우에는 형식을 클래스로 정의 해야 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임 워크 디자인 지침](index.md)
