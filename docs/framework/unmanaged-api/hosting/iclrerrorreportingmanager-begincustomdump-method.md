---
title: ICLRErrorReportingManager::BeginCustomDump 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cb6cd8d31e01ea2f1749a6cb4d17173679f0c06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984791"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="e518d-102">ICLRErrorReportingManager::BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="e518d-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="e518d-103">오류 보고에 대 한 사용자 지정 힙 덤프 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e518d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e518d-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e518d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e518d-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="e518d-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) 사용자 지정 힙 덤프를 작성 하는 힙 덤프의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="e518d-107">[in] 길이 `items` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="e518d-108">하는 경우 `dwFlavor` DUMP_FLAVOR_Mini, 아닙니다 `dwNumItems` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="e518d-109">[in] 배열을 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 경우 미니 덤프에 추가할 항목을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="e518d-110">하는 경우 `dwFlavor` DUMP_FLAVOR_Mini, 아닙니다 `items` null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="e518d-111">[in] 사용 하도록 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e518d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="e518d-112">Return Value</span></span>  
  
|<span data-ttu-id="e518d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e518d-113">HRESULT</span></span>|<span data-ttu-id="e518d-114">설명</span><span class="sxs-lookup"><span data-stu-id="e518d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e518d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e518d-115">S_OK</span></span>|<span data-ttu-id="e518d-116">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="e518d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e518d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e518d-118">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e518d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e518d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e518d-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-120">The call timed out.</span></span>|  
|<span data-ttu-id="e518d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e518d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e518d-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e518d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e518d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e518d-124">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e518d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e518d-125">E_FAIL</span></span>|<span data-ttu-id="e518d-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e518d-127">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e518d-128">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e518d-129">설명</span><span class="sxs-lookup"><span data-stu-id="e518d-129">Remarks</span></span>  
 <span data-ttu-id="e518d-130">`BeginCustomDump` 메서드는 사용자 지정 힙 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="e518d-131">합니다 [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) 메서드를 사용자 지정 힙 덤프 구성 지워지고 연결 된 모든 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="e518d-132">사용자 지정 힙 덤프에서 완료 된 후 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e518d-133">호출 하지 못하면 `EndCustomDump` 메모리 누수를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e518d-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e518d-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e518d-134">Requirements</span></span>  
 <span data-ttu-id="e518d-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e518d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e518d-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e518d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e518d-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e518d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e518d-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e518d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e518d-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="e518d-139">See also</span></span>

- [<span data-ttu-id="e518d-140">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="e518d-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="e518d-141">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="e518d-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="e518d-142">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e518d-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
