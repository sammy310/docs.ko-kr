---
title: ICLRErrorReportingManager::EndCustomDump 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a262ab26c9bbb93e42a11217fbeea6b3c55c7eb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966263"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="4e946-102">ICLRErrorReportingManager::EndCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="4e946-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="4e946-103">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 메서드에 대 한 이전 호출에서 지정 된 사용자 지정 스택 덤프 구성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e946-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e946-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4e946-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="4e946-105">Return Value</span></span>  
  
|<span data-ttu-id="4e946-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e946-106">HRESULT</span></span>|<span data-ttu-id="4e946-107">Description</span><span class="sxs-lookup"><span data-stu-id="4e946-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e946-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e946-108">S_OK</span></span>|<span data-ttu-id="4e946-109">`EndCustomDump`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="4e946-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e946-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e946-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e946-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e946-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e946-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-113">The call timed out.</span></span>|  
|<span data-ttu-id="4e946-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e946-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e946-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e946-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e946-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e946-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e946-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e946-118">E_FAIL</span></span>|<span data-ttu-id="4e946-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e946-120">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e946-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e946-122">설명</span><span class="sxs-lookup"><span data-stu-id="4e946-122">Remarks</span></span>  
 <span data-ttu-id="4e946-123">메서드 `EndCustomDump` 는 `BeginCustomDump` 메서드에 대 한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지우고 연결 된 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="4e946-124">사용자 지정 스택 덤프가 완료 된 후이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4e946-125">호출 `EndCustomDump` 하지 못하면 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e946-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e946-126">Requirements</span></span>  
 <span data-ttu-id="4e946-127">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e946-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e946-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e946-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e946-129">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e946-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e946-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e946-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e946-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e946-131">See also</span></span>

- [<span data-ttu-id="4e946-132">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="4e946-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="4e946-133">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="4e946-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="4e946-134">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e946-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
