---
description: '자세한 정보: WF의 오류 처리 작업'
title: WF의 오류 처리 활동
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: ef26c47d8d99f2d2186ef02820f9bebe691c2ff8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742452"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="0a0cd-103">WF의 오류 처리 활동</span><span class="sxs-lookup"><span data-stu-id="0a0cd-103">Error Handling Activities in WF</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="0a0cd-104">에서는 오류 처리 및 복구를 구현하기 위해 여러 시스템 제공 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0cd-104">provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="0a0cd-105">자세한 내용은 [예외](exceptions.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0cd-105">For more information, see [Exceptions](exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="0a0cd-106">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="0a0cd-106">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="0a0cd-107">`TryCatch` 활동에서 throw된 마지막 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0cd-107">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="0a0cd-108">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0cd-108">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="0a0cd-109">예외 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0cd-109">Implements exception handling.</span></span>|
