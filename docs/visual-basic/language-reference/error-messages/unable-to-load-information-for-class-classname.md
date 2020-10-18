---
title: "'<classname>' 클래스에 대한 정보를 로드할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161610"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="364fe-102">BC30712: ' ' 클래스에 대 한 정보를 로드할 수 없습니다. \<classname></span><span class="sxs-lookup"><span data-stu-id="364fe-102">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="364fe-103">사용할 수 없는 클래스에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="364fe-103">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="364fe-104">**오류 ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="364fe-104">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="364fe-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="364fe-105">To correct this error</span></span>

1. <span data-ttu-id="364fe-106">클래스가 정의 되었고 이름을 올바르게 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="364fe-106">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="364fe-107">모듈에 선언된 멤버 중 하나에 액세스해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="364fe-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="364fe-108">선언된 모듈이 아직 로드되지 않아 디버깅 환경에서 멤버를 찾을 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364fe-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="364fe-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="364fe-109">See also</span></span>

- [<span data-ttu-id="364fe-110">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="364fe-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
