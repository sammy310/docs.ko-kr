---
description: '자세한 정보: 끝점: 승인 되지 않은 초당 보안 호출 수'
title: '엔드포인트: Security Calls Not Authorized Per Second'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 55a49091426538304aceda52308e3f8df2010d6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655463"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="86cde-103">엔드포인트: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="86cde-103">Endpoint: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="86cde-104">카운터 이름: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="86cde-104">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="86cde-105">설명</span><span class="sxs-lookup"><span data-stu-id="86cde-105">Description</span></span>  

 <span data-ttu-id="86cde-106">올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없는 경우에 1초당 들어오는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="86cde-106">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="86cde-107">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="86cde-107">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="86cde-108">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="86cde-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="86cde-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="86cde-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
