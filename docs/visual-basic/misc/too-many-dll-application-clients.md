---
title: DLL 애플리케이션 클라이언트가 너무 많습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
ms.openlocfilehash: 3d6fa507a754447c33e08c90805755b4a379a09f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398528"
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="d561d-102">DLL 애플리케이션 클라이언트가 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d561d-102">Too many DLL application clients</span></span>
<span data-ttu-id="d561d-103">Visual Basic에 대 한 DLL (동적 연결 라이브러리)은 제한 된 수의 호스트 응용 프로그램 에서만 액세스를 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d561d-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="d561d-104">응용 프로그램 및 호스트 Visual Basic (일부는 응용 프로그램에서 액세스할 수 있음) 응용 프로그램은 모두 동시에 Visual Basic DLL에 액세스 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d561d-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d561d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d561d-105">To correct this error</span></span>  
  
- <span data-ttu-id="d561d-106">Visual Basic 액세스 하는 열려 있는 응용 프로그램 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d561d-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d561d-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d561d-107">See also</span></span>

- [<span data-ttu-id="d561d-108">오류 유형</span><span class="sxs-lookup"><span data-stu-id="d561d-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)
