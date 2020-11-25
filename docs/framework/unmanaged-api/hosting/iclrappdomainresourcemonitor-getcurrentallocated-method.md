---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
ms.openlocfilehash: d3bd948dfe4a5cf97e3e3e430f551e7bc6404690
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700797"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="34f45-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="34f45-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="34f45-103">가비지 수집 된 메모리를 빼서 응용 프로그램 도메인이 만들어진 후에 적용 된 모든 메모리 할당의 총 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f45-104">구문</span><span class="sxs-lookup"><span data-stu-id="34f45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34f45-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34f45-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="34f45-106">진행 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="34f45-107">제한이 모든 메모리 할당의 총 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34f45-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="34f45-108">Return Value</span></span>  

 <span data-ttu-id="34f45-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="34f45-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34f45-110">HRESULT</span></span>|<span data-ttu-id="34f45-111">설명</span><span class="sxs-lookup"><span data-stu-id="34f45-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34f45-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="34f45-112">S_OK</span></span>|<span data-ttu-id="34f45-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="34f45-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="34f45-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="34f45-115">응용 프로그램 도메인이 언로드 되었거나 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34f45-116">설명</span><span class="sxs-lookup"><span data-stu-id="34f45-116">Remarks</span></span>  

 <span data-ttu-id="34f45-117">이 메서드는 관리 되는 속성에 해당 하는 관리 되지 않는 <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f45-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34f45-118">Requirements</span></span>  

 <span data-ttu-id="34f45-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f45-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f45-120">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="34f45-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34f45-121">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f45-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34f45-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f45-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f45-123">참조</span><span class="sxs-lookup"><span data-stu-id="34f45-123">See also</span></span>

- [<span data-ttu-id="34f45-124">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34f45-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="34f45-125">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="34f45-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="34f45-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34f45-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="34f45-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="34f45-127">Hosting</span></span>](index.md)
