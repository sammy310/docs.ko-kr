---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8022428c7f803f96e2fa150588edf95542bf19b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169860"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="ef460-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드</span><span class="sxs-lookup"><span data-stu-id="ef460-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="ef460-103">응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 하는 동안 모든 스레드에서 사용 된 총 프로세서 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef460-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef460-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef460-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef460-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="ef460-106">[in] 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="ef460-107">[out] 응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 하는 동안 모든 스레드에서 사용 된 총 프로세서 시간에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="ef460-108">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef460-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ef460-109">Return Value</span></span>  
  
|<span data-ttu-id="ef460-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef460-110">HRESULT</span></span>|<span data-ttu-id="ef460-111">설명</span><span class="sxs-lookup"><span data-stu-id="ef460-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef460-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef460-112">S_OK</span></span>|<span data-ttu-id="ef460-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="ef460-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="ef460-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="ef460-115">응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="ef460-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef460-116">E_FAIL</span></span>|<span data-ttu-id="ef460-117">응용 프로그램 도메인 리소스 모니터링 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="ef460-118">또는</span><span class="sxs-lookup"><span data-stu-id="ef460-118">-or-</span></span><br /><br /> <span data-ttu-id="ef460-119">다른 모든 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef460-120">설명</span><span class="sxs-lookup"><span data-stu-id="ef460-120">Remarks</span></span>  
 <span data-ttu-id="ef460-121">이 메서드는 관리 되는 관리 되지 않는 해당 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef460-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef460-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef460-122">Requirements</span></span>  
 <span data-ttu-id="ef460-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef460-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef460-124">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ef460-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ef460-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ef460-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ef460-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ef460-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef460-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef460-127">See also</span></span>

- [<span data-ttu-id="ef460-128">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef460-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="ef460-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef460-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ef460-130">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="ef460-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="ef460-131">호스팅</span><span class="sxs-lookup"><span data-stu-id="ef460-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
