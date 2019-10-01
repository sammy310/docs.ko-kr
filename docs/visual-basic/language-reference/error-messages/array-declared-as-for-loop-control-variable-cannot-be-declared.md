---
title: For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9e8bb7b79b5a770c3c92e47d8e7c01c5b83d6061
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701205"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="0ff7d-102">For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="0ff7d-103">@No__t-0 루프는 배열을 해당 *요소* 반복 변수로 사용 하지만 해당 배열을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="0ff7d-104">다음 문은이 오류를 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-104">The following statements show how this error can be generated.</span></span>  
  
```vb  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="0ff7d-105">첫 번째 `For Each` 문은 `arrayList`의 요소에 액세스 하는 올바른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="0ff7d-106">두 번째 `For Each` 문은이 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="0ff7d-107">**오류 ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="0ff7d-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ff7d-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0ff7d-108">To correct this error</span></span>  
  
- <span data-ttu-id="0ff7d-109">*요소* 반복 변수의 선언에서 초기화를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff7d-110">참조</span><span class="sxs-lookup"><span data-stu-id="0ff7d-110">See also</span></span>

- [<span data-ttu-id="0ff7d-111">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="0ff7d-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0ff7d-112">배열</span><span class="sxs-lookup"><span data-stu-id="0ff7d-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="0ff7d-113">컬렉션</span><span class="sxs-lookup"><span data-stu-id="0ff7d-113">Collections</span></span>](../../../standard/collections/index.md)
