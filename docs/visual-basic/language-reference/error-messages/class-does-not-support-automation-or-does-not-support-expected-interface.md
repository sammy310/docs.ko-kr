---
title: 클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 856c3f5ef503a7e5919e9e602532c56d9557482f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415403"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="689ad-102">클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="689ad-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="689ad-103">`GetObject` 또는 `CreateObject` 함수 호출에서 지정한 클래스가 프로그래밍 기능 인터페이스를 표시하지 않았거나 프로젝트를 .dll과 .exe 간에 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="689ad-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="689ad-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="689ad-104">To correct this error</span></span>  
  
1. <span data-ttu-id="689ad-105">개체를 만든 애플리케이션 설명서를 참조하여 이 개체 클래스에서 자동화를 사용하는 경우의 제한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="689ad-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="689ad-106">프로젝트를 .dll과 .exe 간에 변경한 경우에는 이전 .dll 또는 .exe의 등록을 수동으로 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="689ad-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689ad-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="689ad-107">See also</span></span>

- [<span data-ttu-id="689ad-108">오류 유형</span><span class="sxs-lookup"><span data-stu-id="689ad-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="689ad-109">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="689ad-109">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
