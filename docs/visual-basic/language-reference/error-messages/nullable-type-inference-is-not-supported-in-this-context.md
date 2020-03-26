---
title: 이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249502"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="ac34b-102">이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac34b-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="ac34b-103">값 형식 및 구조체는 null로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac34b-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="ac34b-104">그러나 형식 추론과 함께 nullable 선언을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac34b-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="ac34b-105">다음 예제에서 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ac34b-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="ac34b-106">**오류 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="ac34b-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac34b-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ac34b-107">To correct this error</span></span>  
  
- <span data-ttu-id="ac34b-108">절을 `As` 사용하여 변수를 nullable 값 문자로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ac34b-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac34b-109">참조</span><span class="sxs-lookup"><span data-stu-id="ac34b-109">See also</span></span>

- [<span data-ttu-id="ac34b-110">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="ac34b-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ac34b-111">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ac34b-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
