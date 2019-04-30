---
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970120"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="71698-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71698-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="71698-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="71698-103">A cyclic operation has failed.</span></span> <span data-ttu-id="71698-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71698-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="71698-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71698-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="71698-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="71698-106">To correct this error</span></span>  
  
- <span data-ttu-id="71698-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71698-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71698-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="71698-108">See also</span></span>

- [<span data-ttu-id="71698-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="71698-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="71698-110">Visual Studio 디버거에서 중단점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71698-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
