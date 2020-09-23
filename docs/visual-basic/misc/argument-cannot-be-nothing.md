---
title: 인수는 Nothing일 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrGeneral_ArgumentNullException
ms.assetid: 2abd995b-36a5-45f0-b3c1-6e0c3b31a875
ms.openlocfilehash: 27c959b0fd62a930750bc731e6ca242b2415f1e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087234"
---
# <a name="argument-cannot-be-nothing"></a><span data-ttu-id="88c9e-102">인수는 Nothing일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88c9e-102">Argument cannot be Nothing</span></span>

<span data-ttu-id="88c9e-103">값이 있어야 하는 인수에 대해 null 값이 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88c9e-103">A null value has been supplied for an argument that must have a value.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88c9e-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="88c9e-104">To correct this error</span></span>  
  
- <span data-ttu-id="88c9e-105">개체의 인스턴스를 제공하지 않고 개체를 사용하려고 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c9e-105">You might have tried to use an object without providing an instance of the object.</span></span> <span data-ttu-id="88c9e-106">이런 경우 `New` 키워드를 사용하여 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88c9e-106">In such a case, use the `New` keyword to create the instance.</span></span>  
  
- <span data-ttu-id="88c9e-107">값이 올바르게 계산되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88c9e-107">Check that the value is calculated correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c9e-108">참조</span><span class="sxs-lookup"><span data-stu-id="88c9e-108">See also</span></span>

- <xref:System.NullReferenceException>
