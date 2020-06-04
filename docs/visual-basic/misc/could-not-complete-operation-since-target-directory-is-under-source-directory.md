---
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376744"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="ac0ee-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0ee-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="ac0ee-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0ee-103">A cyclic operation has failed.</span></span> <span data-ttu-id="ac0ee-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0ee-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="ac0ee-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0ee-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac0ee-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ac0ee-106">To correct this error</span></span>  
  
- <span data-ttu-id="ac0ee-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0ee-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0ee-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac0ee-108">See also</span></span>

- [<span data-ttu-id="ac0ee-109">오류 유형</span><span class="sxs-lookup"><span data-stu-id="ac0ee-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="ac0ee-110">Visual Studio 디버거에서 중단점 사용</span><span class="sxs-lookup"><span data-stu-id="ac0ee-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
