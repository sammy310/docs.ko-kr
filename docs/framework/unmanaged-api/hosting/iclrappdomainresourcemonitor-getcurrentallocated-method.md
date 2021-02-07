---
description: '자세히 알아보기: ICLRAppDomainResourceMonitor:: GetCurrentAllocated 된 메서드'
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
ms.openlocfilehash: d7aaf31f775a9d6e2af95cf1a832c78587a85fe1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753954"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="d01ec-103">ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="d01ec-103">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="d01ec-104">가비지 수집 된 메모리를 빼서 응용 프로그램 도메인이 만들어진 후에 적용 된 모든 메모리 할당의 총 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-104">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d01ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="d01ec-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d01ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d01ec-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="d01ec-107">진행 요청 된 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-107">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="d01ec-108">제한이 모든 메모리 할당의 총 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-108">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d01ec-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d01ec-109">Return Value</span></span>  

 <span data-ttu-id="d01ec-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d01ec-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d01ec-111">HRESULT</span></span>|<span data-ttu-id="d01ec-112">설명</span><span class="sxs-lookup"><span data-stu-id="d01ec-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d01ec-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d01ec-113">S_OK</span></span>|<span data-ttu-id="d01ec-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d01ec-115">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d01ec-115">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d01ec-116">응용 프로그램 도메인이 언로드 되었거나 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-116">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d01ec-117">설명</span><span class="sxs-lookup"><span data-stu-id="d01ec-117">Remarks</span></span>  

 <span data-ttu-id="d01ec-118">이 메서드는 관리 되는 속성에 해당 하는 관리 되지 않는 <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-118">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d01ec-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d01ec-119">Requirements</span></span>  

 <span data-ttu-id="d01ec-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d01ec-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d01ec-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="d01ec-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d01ec-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01ec-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d01ec-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d01ec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d01ec-124">참조</span><span class="sxs-lookup"><span data-stu-id="d01ec-124">See also</span></span>

- [<span data-ttu-id="d01ec-125">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d01ec-125">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="d01ec-126">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="d01ec-126">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d01ec-127">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d01ec-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d01ec-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="d01ec-128">Hosting</span></span>](index.md)
