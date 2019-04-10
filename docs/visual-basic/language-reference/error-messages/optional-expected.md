---
title: "'Optional'이 필요합니다."
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 71a25784f357a7e596093b314ed5b3d721d6f92c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341883"
---
# <a name="optional-expected"></a><span data-ttu-id="1a8f3-102">'Optional'이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f3-102">'Optional' expected</span></span>
<span data-ttu-id="1a8f3-103">프로시저 선언에서 선택적 인수는 필수 인수가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f3-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="1a8f3-104">모든 인수는 선택적 인수 뒤에 선택적 수도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f3-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="1a8f3-105">**오류 ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="1a8f3-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1a8f3-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1a8f3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="1a8f3-107">인수는 필요할 경우에 인수 목록의 첫 번째 선택적 인수 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f3-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="1a8f3-108">선택적 인수는 사용 하는 경우 사용 된 `Optional` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f3-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8f3-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a8f3-109">See also</span></span>

- [<span data-ttu-id="1a8f3-110">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a8f3-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
