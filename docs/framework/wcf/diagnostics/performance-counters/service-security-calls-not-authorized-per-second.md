---
title: '서비스: Security Calls Not Authorized Per Second'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 59e044f7c5946b32d959119939f972e081a8f57b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540493"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="1453b-102">서비스: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="1453b-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="1453b-103">카운터 이름: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="1453b-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="1453b-104">Description</span><span class="sxs-lookup"><span data-stu-id="1453b-104">Description</span></span>  
 <span data-ttu-id="1453b-105">올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없는 경우에 초당 들어오는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1453b-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="1453b-106">이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1453b-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="1453b-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="1453b-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1453b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1453b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
