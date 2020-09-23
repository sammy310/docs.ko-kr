---
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079141"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="95156-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95156-102">Could not complete operation since target directory is under source directory</span></span>

<span data-ttu-id="95156-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="95156-103">A cyclic operation has failed.</span></span> <span data-ttu-id="95156-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95156-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="95156-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95156-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95156-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="95156-106">To correct this error</span></span>  
  
- <span data-ttu-id="95156-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95156-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95156-108">참조</span><span class="sxs-lookup"><span data-stu-id="95156-108">See also</span></span>

- [<span data-ttu-id="95156-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="95156-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="95156-110">Visual Studio 디버거에서 중단점 사용</span><span class="sxs-lookup"><span data-stu-id="95156-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
