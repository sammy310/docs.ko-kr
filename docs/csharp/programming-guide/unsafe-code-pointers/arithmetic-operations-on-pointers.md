---
title: 포인터에 대한 산술 연산 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: bfa81bc926b4fe81455cecb88bc55f4dcd69268e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977840"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>포인터에 대한 산술 연산(C# 프로그래밍 가이드)
이 항목에서는 산술 연산자 `+` 및 `-`를 사용하여 포인터를 조작하는 방법을 설명합니다.  
  
> [!NOTE]
>  void 포인터에 대해 산술 연산을 수행할 수 없습니다.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>포인터에 숫자 값 더하기 및 포인터에서 숫자 값 빼기  
 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식의 `n` 값을 포인터에 더할 수 있습니다. `p`가 `pointer-type*` 형식의 포인터인 경우 결과 `p+n`은 `p`의 주소에 `n * sizeof(pointer-type)`를 더하여 생성된 포인터입니다. 마찬가지로 `p-n`은 `p` 주소에서 `n * sizeof(pointer-type)`를 뺀 결과로 생성된 포인터입니다.  
  
## <a name="subtracting-pointers"></a>포인터 빼기  
 같은 형식의 포인터를 뺄 수도 있습니다. 결과는 항상 `long` 형식입니다. 예를 들어 `p1` 및 `p2`가 `pointer-type*` 형식의 포인터인 경우 `p1-p2` 식의 결과는 다음과 같습니다.  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 산술 연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [C# 연산자](../../../csharp/language-reference/operators/index.md)
- [포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [유형](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
