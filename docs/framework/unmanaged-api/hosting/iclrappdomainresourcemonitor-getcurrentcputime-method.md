---
description: '자세히 알아보기: ICLRAppDomainResourceMonitor:: GetCurrentCpuTime 메서드'
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: ce36bf4ab88f953834d3ff12404bcaadcb42812d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753931"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="14f28-103">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드</span><span class="sxs-lookup"><span data-stu-id="14f28-103">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>

<span data-ttu-id="14f28-104">응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-104">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f28-105">구문</span><span class="sxs-lookup"><span data-stu-id="14f28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14f28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14f28-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="14f28-107">진행 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-107">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="14f28-108">제한이 응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-108">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="14f28-109">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-109">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14f28-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="14f28-110">Return Value</span></span>  
  
|<span data-ttu-id="14f28-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14f28-111">HRESULT</span></span>|<span data-ttu-id="14f28-112">설명</span><span class="sxs-lookup"><span data-stu-id="14f28-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14f28-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="14f28-113">S_OK</span></span>|<span data-ttu-id="14f28-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="14f28-115">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="14f28-115">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="14f28-116">응용 프로그램 도메인이 언로드 되었거나 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-116">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="14f28-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14f28-117">E_FAIL</span></span>|<span data-ttu-id="14f28-118">응용 프로그램 도메인 리소스 모니터링이 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-118">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="14f28-119">또는</span><span class="sxs-lookup"><span data-stu-id="14f28-119">-or-</span></span><br /><br /> <span data-ttu-id="14f28-120">다른 모든 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-120">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14f28-121">설명</span><span class="sxs-lookup"><span data-stu-id="14f28-121">Remarks</span></span>  

 <span data-ttu-id="14f28-122">이 메서드는 관리 되는 속성에 해당 하는 관리 되지 않는 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-122">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f28-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14f28-123">Requirements</span></span>  

 <span data-ttu-id="14f28-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14f28-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14f28-125">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="14f28-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="14f28-126">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14f28-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14f28-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f28-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f28-128">참조</span><span class="sxs-lookup"><span data-stu-id="14f28-128">See also</span></span>

- [<span data-ttu-id="14f28-129">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14f28-129">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="14f28-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14f28-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="14f28-131">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="14f28-131">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="14f28-132">호스팅</span><span class="sxs-lookup"><span data-stu-id="14f28-132">Hosting</span></span>](index.md)
