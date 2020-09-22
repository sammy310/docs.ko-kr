---
title: 이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: f2d3bcdaccfd993da1eebf81ae961f35eb22b294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873685"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="5fdc0-102">이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fdc0-102">Nullable type inference is not supported in this context</span></span>

<span data-ttu-id="5fdc0-103">값 형식과 구조체를 nullable로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fdc0-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="5fdc0-104">그러나 nullable 선언을 형식 유추와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fdc0-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="5fdc0-105">다음 예에서는이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fdc0-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="5fdc0-106">**오류 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="5fdc0-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5fdc0-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5fdc0-107">To correct this error</span></span>  
  
- <span data-ttu-id="5fdc0-108">`As`절을 사용 하 여 변수를 nullable 값 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fdc0-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fdc0-109">참조</span><span class="sxs-lookup"><span data-stu-id="5fdc0-109">See also</span></span>

- [<span data-ttu-id="5fdc0-110">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="5fdc0-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="5fdc0-111">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="5fdc0-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
