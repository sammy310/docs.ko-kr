---
title: void - C# 참조
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742766"
---
# <a name="void-c-reference"></a>void(C# 참조)

메서드에 대한 반환 형식으로 사용될 경우 `void`는 메서드가 값을 반환하지 않도록 지정합니다.

`void`는 메서드의 매개 변수 목록에서 허용되지 않습니다. 매개 변수를 사용하지 않고 값을 반환하지 않는 메서드는 다음과 같이 선언됩니다.

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

`void`는 또한 알 수 없는 형식에 대한 포인터를 선언하기 위해 안전하지 않은 컨텍스트에서도 사용됩니다. 자세한 내용은 [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.

`void`는 .NET Framework <xref:System.Void?displayProperty=nameWithType> 형식의 별칭입니다.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 키워드](index.md)
- [참조 형식](reference-types.md)
- [값 형식](../builtin-types/value-types.md)
- [메서드](../../programming-guide/classes-and-structs/methods.md)
- [안전하지 않은 코드 및 포인터](../../programming-guide/unsafe-code-pointers/index.md)
