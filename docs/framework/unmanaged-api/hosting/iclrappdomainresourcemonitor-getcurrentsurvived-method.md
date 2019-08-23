---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950156"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="d8855-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드</span><span class="sxs-lookup"><span data-stu-id="d8855-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="d8855-103">마지막 전체 차단 가비지 수집을 수행 하 고 현재 응용 프로그램 도메인에서 참조 하는 바이트 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8855-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8855-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8855-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8855-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d8855-106">진행 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="d8855-107">제한이 이 응용 프로그램 도메인에서 보유 하 고 있는 마지막 가비지 수집 후에도 남아 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="d8855-108">전체 수집 후에이 수는 정확 하 고 완전 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="d8855-109">임시 수집 후에이 수는 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="d8855-110">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="d8855-111">제한이 마지막 가비지 수집에서 남아 있는 총 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="d8855-112">전체 컬렉션 후에이 수는 관리 되는 힙에서 보유 되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="d8855-113">임시 수집 후에이 수는 임시 생성에 실시간으로 저장 되는 바이트 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="d8855-114">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8855-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="d8855-115">Return Value</span></span>  
 <span data-ttu-id="d8855-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d8855-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8855-117">HRESULT</span></span>|<span data-ttu-id="d8855-118">설명</span><span class="sxs-lookup"><span data-stu-id="d8855-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8855-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8855-119">S_OK</span></span>|<span data-ttu-id="d8855-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="d8855-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d8855-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d8855-122">응용 프로그램 도메인이 언로드 되었거나 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8855-123">설명</span><span class="sxs-lookup"><span data-stu-id="d8855-123">Remarks</span></span>  
 <span data-ttu-id="d8855-124">통계는 전체 차단 가비지 수집 후에만 업데이트 됩니다. 즉, 컬렉션이 발생 하는 동안 응용 프로그램을 중지 하는 모든 세대를 포함 하는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="d8855-125">예를 들어를 <xref:System.GC.Collect?displayProperty=nameWithType> 메서드 오버 로드는 전체 차단 컬렉션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="d8855-126">동시 가비지 수집은 백그라운드에서 발생 하 고 응용 프로그램을 차단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="d8855-127">메서드 `GetCurrentSurvived` 는 관리 되 <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> 는 속성에 해당 하는 관리 되지 않는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8855-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8855-128">Requirements</span></span>  
 <span data-ttu-id="d8855-129">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8855-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8855-130">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d8855-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d8855-131">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8855-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8855-132">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8855-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8855-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8855-133">See also</span></span>

- [<span data-ttu-id="d8855-134">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8855-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="d8855-135">애플리케이션 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="d8855-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d8855-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8855-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d8855-137">호스팅</span><span class="sxs-lookup"><span data-stu-id="d8855-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
