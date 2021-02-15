---
description: '자세한 정보: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.'
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 5fb0bf1d761faf9d3d0c64e8815e28e14841b1fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463522"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="b15c3-103">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b15c3-103">Could not complete operation since target directory is under source directory</span></span>

<span data-ttu-id="b15c3-104">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="b15c3-104">A cyclic operation has failed.</span></span> <span data-ttu-id="b15c3-105">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b15c3-105">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="b15c3-106">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15c3-106">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b15c3-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b15c3-107">To correct this error</span></span>  
  
- <span data-ttu-id="b15c3-108">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15c3-108">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15c3-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b15c3-109">See also</span></span>

- [<span data-ttu-id="b15c3-110">오류 유형</span><span class="sxs-lookup"><span data-stu-id="b15c3-110">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="b15c3-111">Visual Studio 디버거에서 중단점 사용</span><span class="sxs-lookup"><span data-stu-id="b15c3-111">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
