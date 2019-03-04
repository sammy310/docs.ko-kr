---
title: '방법: 포인터 증가 및 감소 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 358decb73666d5a5ef7c0fa828168d90d2c22c1e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973706"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)

증가 및 감소 연산자인 `++` 및 `--`를 사용하여 `pointer-type*` 형식의 포인터에 대한 포인터 위치를 `sizeof(pointer-type)`만큼 변경합니다. 증가 및 감소 식은 다음 형식을 사용합니다.  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 `void*` 형식을 제외한 모든 형식의 포인터에 증가 및 감소 연산자를 적용할 수 있습니다.  
  
 `pointer-type*` 형식의 포인터에 증가 연산자를 적용할 경우 포인터 변수에 포함된 주소에 `sizeof(pointer-type)`를 더하는 효과가 있습니다.  
  
 `pointer-type*` 형식의 포인터에 감소 연산자를 적용할 경우 포인터 변수에 포함된 주소에서 `sizeof(pointer-type)`를 빼는 효과가 있습니다.  
  
 연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 포인터를 `int` 크기만큼 증가하여 배열을 단계별로 실행합니다. 각 단계에서 주소와 배열 요소의 내용을 표시합니다.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#13)]  
  
**Value:0 @ 주소:12860272**
**Value:1 @ 주소:12860276**
**Value:2 @ 주소:12860280**
**Value:3 @ 주소:12860284**
**Value:4 @ 주소:12860288**

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [C# 연산자](../../../csharp/language-reference/operators/index.md)
- [포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [유형](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
- [sizeof](../../../csharp/language-reference/keywords/sizeof.md)
