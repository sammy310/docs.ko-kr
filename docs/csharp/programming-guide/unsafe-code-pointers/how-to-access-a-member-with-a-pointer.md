---
title: '방법: 포인터로 멤버에 액세스 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200353"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>방법: 포인터로 멤버에 액세스(C# 프로그래밍 가이드)
안전하지 않은 컨텍스트에서 선언된 구조체 멤버에 액세스하기 위해 다음 예제에 제시된 멤버 액세스 연산자를 사용할 수 있습니다. 여기에서 `p`는 멤버 `x`가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md)에 대한 포인터입니다.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 `x` 및 `y`라는 두 좌표가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md) `CoOrds`를 선언하고 인스턴스화합니다. 멤버 액세스 연산자 `->`와 인스턴스 `home`에 대한 포인터를 사용하면 `x`와 `y`에 값이 할당됩니다.  
  
> [!NOTE]
>  `p->x` 식은 `(*p).x` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [유형](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
