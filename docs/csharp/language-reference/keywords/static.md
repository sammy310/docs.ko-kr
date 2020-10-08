---
description: static 한정자 - C# 참조
title: static 한정자 - C# 참조
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 239163fc2f91ccbfe8b1c111a358db87d36a8308
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654641"
---
# <a name="static-c-reference"></a>static(C# 참조)

이 페이지에서는 `static` 한정자 키워드를 다룹니다. `static` 키워드는 [`using static`](using-static.md) 지시문의 일부이기도 합니다.

`static` 한정자를 사용하여 특정 개체가 아니라 형식 자체에 속하는 정적 멤버를 선언할 수 있습니다. `static` 한정자를 사용하여 `static` 클래스를 선언할 수 있습니다. 클래스, 인터페이스 및 구조체에서 필드, 메서드, 속성, 연산자, 이벤트 및 생성자에 `static` 한정자를 추가할 수 있습니다. `static` 한정자는 인덱서 또는 종료자와 함께 사용할 수 없습니다. 자세한 내용은 [static 클래스 및 static 클래스 멤버](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.

C# 8.0부터 `static` 한정자를 [로컬 함수](../../programming-guide/classes-and-structs/local-functions.md)에 추가할 수 있습니다. 정적 로컬 함수는 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.

C# 9.0부터 [람다 식](../operators/lambda-expressions.md) 또는 [무명 메서드](../operators/delegate-operator.md)에 `static` 한정자를 추가할 수 있습니다. 정적 람다 또는 무명 메서드는 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.

## <a name="example---static-class"></a>예제 - 정적 클래스

다음 클래스는 `static`으로 선언되며 `static` 메서드만 포함합니다.

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

상수 또는 형식 선언은 암시적으로 `static` 구성원입니다. `static` 구성원은 인스턴스를 통해 참조할 수 없습니다. 대신, 형식 이름을 통해 참조됩니다. 예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

`static` 구성원 `x`를 참조하려면 동일한 범위에서 구성원에 액세스할 수 없는 경우 정규화된 이름인 `MyBaseC.MyStruct.x`를 사용합니다.

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

클래스 인스턴스에는 클래스의 모든 인스턴스 필드에 대한 별도 복사본이 포함되지만 각 `static` 필드의 복사본은 한 개만 있습니다.

[`this`](this.md)를 사용하여 `static` 메서드 또는 속성 접근자를 참조할 수는 없습니다.

`static` 키워드가 클래스에 적용된 경우 클래스의 모든 구성원은 `static`이어야 합니다.

클래스, 인터페이스 및 `static` 클래스에 `static` 생성자가 있을 수 있습니다. 프로그램이 시작되어 클래스가 인스턴스화되기 전에 `static` 생성자가 호출됩니다.

> [!NOTE]
> `static` 키워드는 C++보다 사용이 제한적입니다. C++ 키워드와 비교하려면 [스토리지 클래스(C++)](/cpp/cpp/storage-classes-cpp#static)를 참조하세요.

`static` 구성원을 보여 주려면 회사 직원을 나타내는 클래스를 고려해 보세요. 클래스에 직원 수를 구하는 메서드와 직원 수를 저장하는 필드가 포함되어 있다고 가정합니다. 메서드와 필드는 둘 다 직원 인스턴스에 속하지 않습니다. 대신 직원의 클래스에 전체적으로 속합니다. 클래스의 `static` 구성원으로 선언해야 합니다.

## <a name="example---static-field-and-method"></a>예제 - 정적 필드 및 메서드

이 예제에서는 새 직원의 이름 및 ID를 읽고, 직원 카운터를 1만큼 늘린 다음 새 직원에 대한 정보와 새 직원 수를 표시합니다. 이 프로그램은 키보드에서 현재 직원 수를 읽습니다.

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a>예제 - 정적 초기화

이 예제에서는 아직 선언되지 않은 다른 `static` 필드를 사용하여 `static` 필드를 초기화할 수 있음을 보여 줍니다. `static` 필드에 값을 명시적으로 할당할 때까지 결과는 정의되지 않습니다.

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [한정자](index.md)
- [using 정적 지시문](using-static.md)
- [정적 클래스 및 정적 클래스 멤버](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
