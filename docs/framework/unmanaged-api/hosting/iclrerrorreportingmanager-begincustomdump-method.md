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
ms.openlocfilehash: 7153ac214ab99228ac9c59032aa8248d06d14c3b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129306"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="57809-102">ICLRErrorReportingManager::BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="57809-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="57809-103">오류 보고에 대 한 사용자 지정 힙 덤프의 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57809-104">구문</span><span class="sxs-lookup"><span data-stu-id="57809-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57809-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57809-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="57809-106">진행 사용자 지정 힙 덤프를 빌드할 힙 덤프의 종류를 나타내는 [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="57809-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="57809-107">진행 `items` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="57809-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="57809-108">`dwFlavor` DUMP_FLAVOR_Mini이 아니면 `dwNumItems` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="57809-109">진행 미니 덤프에 추가할 항목을 지정 하는 [Custom덤프 항목](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 인스턴스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="57809-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="57809-110">`dwFlavor` DUMP_FLAVOR_Mini이 아닌 경우 `items`은 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="57809-111">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57809-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="57809-112">Return Value</span></span>  
  
|<span data-ttu-id="57809-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57809-113">HRESULT</span></span>|<span data-ttu-id="57809-114">설명</span><span class="sxs-lookup"><span data-stu-id="57809-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57809-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="57809-115">S_OK</span></span>|<span data-ttu-id="57809-116">메서드가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="57809-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57809-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57809-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57809-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57809-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57809-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-120">The call timed out.</span></span>|  
|<span data-ttu-id="57809-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57809-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57809-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57809-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57809-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57809-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57809-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57809-125">E_FAIL</span></span>|<span data-ttu-id="57809-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57809-127">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57809-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57809-128">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57809-129">주의</span><span class="sxs-lookup"><span data-stu-id="57809-129">Remarks</span></span>  
 <span data-ttu-id="57809-130">`BeginCustomDump` 메서드는 사용자 지정 힙 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="57809-131">[Endcustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) 메서드는 사용자 지정 힙 덤프 구성을 지우고 연결 된 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="57809-132">사용자 지정 힙 덤프가 완료 된 후이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="57809-133">`EndCustomDump` 호출 하지 못하면 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57809-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57809-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57809-134">Requirements</span></span>  
 <span data-ttu-id="57809-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57809-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57809-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="57809-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57809-137">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57809-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57809-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57809-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57809-139">참조</span><span class="sxs-lookup"><span data-stu-id="57809-139">See also</span></span>

- [<span data-ttu-id="57809-140">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="57809-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="57809-141">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="57809-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="57809-142">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57809-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
