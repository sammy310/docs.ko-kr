---
title: 형식과 그 멤버 정의하기 - C# 둘러보기
description: 형식은 프로그램의 기본적인 구성 요소입니다. C#에서 클래스, 구조체, 인터페이스 등을 만드는 방법을 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: efd353fe8c1e6a57952bcb2586a05ad38ecd52b9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "88559117"
---
# <a name="types-and-members"></a>형식 및 멤버

## <a name="classes-and-objects"></a>클래스 및 개체

*클래스* 는 C#의 가장 기본적인 형식입니다. 클래스는 상태(필드)와 작업(메서드 및 기타 함수 멤버)을 하나의 단위로 결합하는 데이터 구조입니다. 클래스는 해당 클래스의 ‘인스턴스’(‘개체’라고도 함)에 대한 정의를 제공합니다.  클래스는 *상속* 및 *다형성* 과 *파생된 클래스* 가 *기본 클래스* 를 확장하고 특수화할 수 있는 메커니즘을 지원합니다.

새 클래스는 클래스 선언을 사용하여 만들어집니다. 클래스 선언은 헤더로 시작합니다. 헤더는 다음을 지정합니다.

- 클래스의 특성 및 한정자
- 클래스의 이름
- 기본 클래스([기본 클래스](#base-classes)에서 상속하는 경우)
- 이 클래스에서 구현한 인터페이스

헤더 다음에는 구분 기호 `{` 및 `}` 간에 작성되는 멤버 선언 목록으로 구성되는 클래스 본문이 나옵니다.

다음 코드는 `Point`라는 간단한 클래스의 선언입니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointClass":::

클래스의 인스턴스는 새 인스턴스에 대한 메모리를 할당하고, 인스턴스를 초기화하는 생성자를 호출하고, 인스턴스에 대한 참조를 반환하는 `new` 연산자를 사용하여 만들어집니다. 다음 문은 두 개의 `Point` 개체를 만들고 해당 개체에 대한 참조를 두 변수에 저장합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePoints":::

개체가 차지하는 메모리는 개체에 더 이상 연결할 수 없을 때 자동으로 회수됩니다. C#에서는 개체를 명시적으로 할당 취소할 필요가 없으며 가능하지도 않습니다.

### <a name="type-parameters"></a>형식 매개 변수

제네릭 클래스는 [ **‘형식 매개 변수’** ](../programming-guide/generics/index.md)를 정의합니다.* 형식 매개 변수는 대괄호로 묶인 형식 매개 변수 이름 목록입니다. 형식 매개 변수는 클래스 이름을 따릅니다. 그런 후 형식 매개 변수를 클래스 선언 본문에 사용하여 클래스의 멤버를 정의할 수 있습니다. 다음 예제에서 `Pair`의 형식 매개 변수는 `TFirst` 및 `TSecond`입니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DefinePairClass":::

형식 매개 변수를 사용하도록 선언된 클래스 형식을 ‘제네릭 클래스 형식’이라고 합니다. 구조체, 인터페이스 및 대리자 형식도 제네릭일 수 있습니다.
제네릭 클래스를 사용하는 경우 각 형식 매개 변수에 대해 다음과 같은 형식 인수가 제공되어야 합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePairObject":::

위의 `Pair<int,string>`과 같이 형식 인수가 제공된 제네릭 형식을 *생성된 형식* 이라고 합니다.

### <a name="base-classes"></a>기본 클래스

클래스 선언은 기본 클래스를 지정할 수 있습니다. 클래스 이름 및 형식 매개 변수 뒤에 콜론과 기본 클래스의 이름을 사용하면 됩니다. 기본 클래스 지정을 생략하면 `object` 형식에서 파생되는 클래스와 같습니다. 다음 예제에서 `Point3D`의 기본 클래스는 `Point`입니다. 첫 번째 예제에서 `Point`의 기본 클래스는 `object`입니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="Create3DPoint":::

클래스는 기본 클래스의 멤버를 상속합니다. 상속은 클래스가 기본 클래스의 거의 모든 멤버를 암시적으로 포함함을 의미합니다. 클래스는 인스턴스 및 정적 생성자와 종결자는 상속하지 않습니다. 파생 클래스는 해당 파생된 클래스를 상속하는 멤버에 새 멤버를 추가할 수 있지만 상속된 멤버의 정의를 제거할 수 없습니다. 앞의 예제에서 `Point3D`는 `Point`에서 `X` 및 `Y` 멤버를 상속하고 모든 `Point3D` 인스턴스는 세 개의 속성, 즉 `X`, `Y` 및 `Z`를 포함합니다.

클래스 형식에서 해당 기본 클래스 형식 간에 암시적 변환이 존재합니다. 클래스 형식의 변수는 해당 클래스의 인스턴스 또는 모든 파생 클래스의 인스턴스를 참조할 수 있습니다. 예를 들어 이전 클래스 선언에서 형식 `Point`의 변수는 `Point` 또는 `Point3D`를 참조할 수 있습니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplicitCastToBase":::

## <a name="structs"></a>구조체

클래스는 상속과 다형성을 지원하는 형식을 정의합니다. 이를 통해 파생 클래스의 계층 구조를 기반으로 정교한 동작을 만들 수 있습니다. 이와 대조적으로 [ **‘구조체’** ](../language-reference/builtin-types/struct.md) 형식은 보다 단순한 형식으로, 기본 용도는 데이터 값을 저장하는 것입니다.* 구조체는 기본 형식을 선언할 수 없으며, <xref:System.ValueType?displayProperty=nameWithType>에서 암시적으로 파생됩니다. `struct` 형식에서 다른 `struct` 형식을 파생할 수 없으며 암시적으로 봉인됩니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointStruct":::

## <a name="interfaces"></a>인터페이스

[‘인터페이스’](../programming-guide/interfaces/index.md)는 클래스 및 구조체로 구현할 수 있는 계약을 정의합니다. 인터페이스는 메서드, 속성, 이벤트 및 인덱서를 포함할 수 있습니다. 인터페이스는 일반적으로 해당 인터페이스가 정의하는 멤버의 구현을 제공하지 않으며 단지 해당 인터페이스를 구현하는 클래스 또는 구조체에서 제공해야 하는 멤버를 지정합니다.

인터페이스는 ‘다중 상속’을 사용할 수 있습니다. 다음 예제에서 인터페이스 `IComboBox`는 `ITextBox` 및 `IListBox`를 둘 다 상속합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FirstInterfaces":::

클래스 및 구조체는 여러 인터페이스를 구현할 수 있습니다. 다음 예제에서 클래스 `EditBox`는 `IControl` 및 `IDataBound`를 둘 다 구현합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplementInterfaces":::

클래스 또는 구조체가 특정 인터페이스를 구현하는 경우 해당 클래스 또는 구조체의 인스턴스를 해당 인터페이스 형식으로 암시적으로 변환할 수 있습니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UseInterfaces":::

## <a name="enums"></a>열거형

[‘열거형’](../language-reference/builtin-types/enum.md) 형식은 상수 값 세트를 정의합니다. 다음 `enum`은 여러 뿌리채소를 정의하는 상수를 선언합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="EnumDeclaration":::

플래그와 함께 사용되도록 `enum`을 정의할 수도 있습니다. 다음 선언은 사계절에 대한 플래그 세트를 선언합니다. 모든 계절을 포함하는 `All` 값을 비롯해 계절의 모든 조합을 적용할 수 있습니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FlagsEnumDeclaration":::

다음 예제에서는 위 열거형의 선언을 보여 줍니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UsingEnums":::

## <a name="nullable-types"></a>Nullable 유형

모든 형식의 변수는 ‘null을 허용하지 않는’ 또는 ‘null 허용’으로 선언할 수 있습니다.  null 허용 변수는 값이 없음을 나타내는 추가 `null` 값을 포함할 수 있습니다. null 허용 값 형식(구조체 또는 열거형)은 <xref:System.Nullable%601?displayProperty=nameWithType>로 표현됩니다. null을 허용하지 않는 형식과 null 참조 형식은 모두 기본 참조 형식으로 표현됩니다. 둘 사이의 구분은 컴파일러와 일부 라이브러리에서 읽어 들이는 메타데이터로 표현됩니다. 컴파일러는 null 참조가 먼저 `null`에 대해 값을 검사하지 않고 역참조될 경우 경고를 발생시킵니다. 컴파일러는 null을 허용하지 않는 참조에 `null`일 수 있는 값을 할당하는 경우에도 경고를 표시합니다. 다음 예제에서는 ‘null 허용 int’를 선언하고 `null`로 초기화합니다. 그런 다음 값을 `5`로 설정합니다. 이 예제는 ‘null 허용 문자열’과 동일한 개념을 보여 줍니다. 자세한 내용은 [null 허용 값 형식](../language-reference/builtin-types/nullable-value-types.md) 및 [null 허용 참조 형식](../nullable-references.md)을 참조하세요.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareNullable":::

## <a name="tuples"></a>튜플

C#은 간단한 데이터 구조로 여러 데이터 요소를 그룹화하는 간결한 구문을 제공하는 [‘튜플’](../language-reference/builtin-types/value-tuples.md)을 지원합니다.* 다음 예제에서 볼 수 있듯이 튜플은 `(`와 `)` 사이에서 멤버의 형식과 이름을 선언함으로써 인스턴스화합니다.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareTuples":::

튜플은 다음 문서에서 설명하는 기본 구성 요소를 사용하지 않고도 여러 멤버를 위한 또 다른 데이터 구조를 제공합니다.

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](program-building-blocks.md)
