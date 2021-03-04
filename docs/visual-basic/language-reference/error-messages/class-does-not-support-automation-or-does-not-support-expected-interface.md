---
description: '자세히 알아보기: 클래스가 자동화를 지원 하지 않거나 필요한 인터페이스를 지원 하지 않습니다.'
title: 클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: c173eeddf3a34d6af169b91066199ce7d03cf4ba
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106633"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="d6836-103">클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6836-103">Class does not support Automation or does not support expected interface</span></span>

<span data-ttu-id="d6836-104">`GetObject` 또는 `CreateObject` 함수 호출에서 지정한 클래스가 프로그래밍 기능 인터페이스를 표시하지 않았거나 프로젝트를 .dll과 .exe 간에 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6836-104">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6836-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d6836-105">To correct this error</span></span>  
  
1. <span data-ttu-id="d6836-106">개체를 만든 애플리케이션 설명서를 참조하여 이 개체 클래스에서 자동화를 사용하는 경우의 제한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6836-106">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="d6836-107">프로젝트를 .dll과 .exe 간에 변경한 경우에는 이전 .dll 또는 .exe의 등록을 수동으로 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6836-107">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6836-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6836-108">See also</span></span>

- [<span data-ttu-id="d6836-109">오류 유형</span><span class="sxs-lookup"><span data-stu-id="d6836-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="d6836-110">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="d6836-110">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
