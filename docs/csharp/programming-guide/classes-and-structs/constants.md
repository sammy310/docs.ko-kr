---
title: 상수 - C# 프로그래밍 가이드
description: C#의 상수는 컴파일 시간 리터럴 값이며 프로그램이 컴파일된 후에는 변경되지 않습니다. C# 기본 제공 형식만 상수가 될 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 4783aff8e9424c90e46cb52692a3e645e995d914
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899076"
---
# <a name="constants-c-programming-guide"></a>상수(C# 프로그래밍 가이드)

상수는 컴파일 시간에 알려진 변경할 수 없는 값입니다. 프로그램 수명 동안 변경하지 마세요. 상수는 [const](../../language-reference/keywords/const.md) 한정자로 선언됩니다. C# [기본 제공 형식](../../language-reference/builtin-types/built-in-types.md)(<xref:System.Object?displayProperty=nameWithType> 제외)만 `const`로 선언할 수 있습니다. 클래스, 구조체 및 배열을 비롯한 사용자 정의 형식은 `const`가 될 수 없습니다. [readonly](../../language-reference/keywords/readonly.md) 한정자를 사용하여 런타임에 한 번 초기화되고(예: 생성자에서) 이후 변경할 수 없는 클래스, 구조체 또는 배열을 만듭니다.  
  
 C#에서는 `const` 메서드, 속성 또는 이벤트를 지원하지 않습니다.  
  
 열거형 형식을 사용하여 정수 계열 기본 제공 형식(예: `int`, `uint`, `long` 등)에 대한 명명된 상수를 정의할 수 있습니다. 자세한 내용은 [enum](../../language-reference/builtin-types/enum.md)을 참조하세요.  
  
 상수는 선언될 때 초기화되어야 합니다. 예를 들어:  
  
 [!code-csharp[Calendar#1](snippets/constants/Calendar.cs#1)]
  
 이 예제에서 `Months` 상수는 항상 12이고 클래스 자체에 의해서도 변경될 수 없습니다. 실제로 컴파일러는 C# 소스 코드에서 상수 식별자를 발견할 경우(예: `Months`) 리터럴 값을 직접 컴파일러에서 생성하는 IL(중간 언어) 코드로 대체합니다. 런타임에 상수와 연결된 변수 주소가 없으므로 `const` 필드는 참조를 통해 전달될 수 없고 식에 l-value로 표시될 수 없습니다.  
  
> [!NOTE]
> DLL과 같이 다른 코드에 정의된 상수 값을 참조할 경우 주의하세요. DLL의 새 버전에서 상수의 새 값을 정의할 경우 프로그램은 새 버전에 대해 다시 컴파일될 때까지 이전 리터럴 값을 포함합니다.  
  
 다음과 같이 같은 형식의 여러 상수를 동시에 선언할 수 있습니다.  
  
 [!code-csharp[Calendar#2](snippets/constants/Calendar.cs#2)]
  
 상수를 초기화하는 데 사용되는 식은 순환 참조를 만들지 않을 경우 다른 상수를 참조할 수 있습니다. 예를 들어:  
  
 [!code-csharp[Calendar#3](snippets/constants/Calendar.cs#3)]
  
 상수는 [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)로 표시될 수 있습니다. 이러한 액세스 한정자는 클래스의 사용자가 상수에 액세스하는 방법을 정의합니다. 자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.  
  
 형식의 모든 인스턴스에 대한 상수 값이 같으므로 상수가 [static](../../language-reference/keywords/static.md) 필드인 것처럼 상수에 액세스합니다. 상수를 선언하는 데 `static` 키워드를 사용하지 않습니다. 상수를 정의하는 클래스에 포함되지 않은 식은 상수에 액세스할 때 클래스 이름, 마침표 및 상수 이름을 사용해야 합니다. 예를 들어:  
  
 [!code-csharp[Calendar#4](snippets/constants/Calendar.cs#4)]
  
## <a name="c-language-specification"></a>C# 언어 사양  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](./index.md)
- [속성](./properties.md)
- [형식](../types/index.md)
- [readonly](../../language-reference/keywords/readonly.md)
- [C# 파트 1의 불변성: 불변성의 종류](/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability)
