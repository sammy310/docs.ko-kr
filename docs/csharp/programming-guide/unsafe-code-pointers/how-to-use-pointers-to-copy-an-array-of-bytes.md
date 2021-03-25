---
title: 포인터를 사용하여 바이트 배열을 복사하는 방법 - C# 프로그래밍 가이드
description: 포인터를 사용하여 바이트 배열을 복사하는 방법을 알아봅니다. 코드 예제 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: f0122d29729ac8ad634f39f0643902e9bb78a8a5
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478608"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a>포인터를 사용하여 바이트 배열을 복사하는 방법(C# 프로그래밍 가이드)

다음 예제에서는 포인터를 사용하여 배열 간에 바이트를 복사합니다.

이 예제에서는 `Copy` 메서드에서 포인터를 사용할 수 있도록 하는 [unsafe](../../language-reference/keywords/unsafe.md) 키워드를 사용합니다. [fixed](../../language-reference/keywords/fixed-statement.md) 문은 소스 및 대상 배열에 대한 포인터를 선언하는 데 사용됩니다. `fixed` 명령문은 소스 및 대상 배열의 위치가 메모리에 *고정* 되므로 가비지 수집에 의해 이동되지 않습니다. `fixed` 블록이 완료되면 배열에 대한 메모리 블록이 고정 해제됩니다. 이 예제의 `Copy` 메서드는 `unsafe` 키워드를 사용하므로 [**AllowUnsafeBlocks**](../../language-reference/compiler-options/language.md#allowunsafeblocks) 컴파일러 옵션으로 컴파일해야 합니다.

이 예제에서는 두 번째 관리되지 않는 포인터보다는 인덱스를 사용하여 두 배열의 요소에 액세스합니다. `pSource` 및 `pTarget` 포인터의 선언은 배열을 고정합니다. 이 기능은 C# 7.3부터 사용할 수 있습니다.

## <a name="example"></a>예제

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [안전하지 않은 코드 및 포인터](index.md)
- [**AllowUnsafeBlocks**(C# 컴파일러 옵션)](../../language-reference/compiler-options/language.md#allowunsafeblocks)
- [가비지 수집](../../../standard/garbage-collection/index.md)
