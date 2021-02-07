---
description: '자세히 알아보기: ICLRErrorReportingManager:: EndCustomDump 메서드'
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
ms.openlocfilehash: 406d7d77f4cd63c69fec56acb0819d56c6271630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689471"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="45565-103">ICLRErrorReportingManager::EndCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="45565-103">ICLRErrorReportingManager::EndCustomDump Method</span></span>

<span data-ttu-id="45565-104">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) 메서드에 대 한 이전 호출에서 지정 된 사용자 지정 스택 덤프 구성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="45565-104">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45565-105">구문</span><span class="sxs-lookup"><span data-stu-id="45565-105">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="45565-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="45565-106">Return Value</span></span>  
  
|<span data-ttu-id="45565-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45565-107">HRESULT</span></span>|<span data-ttu-id="45565-108">설명</span><span class="sxs-lookup"><span data-stu-id="45565-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45565-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="45565-109">S_OK</span></span>|<span data-ttu-id="45565-110">`EndCustomDump` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-110">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="45565-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45565-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45565-112">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45565-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45565-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45565-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-114">The call timed out.</span></span>|  
|<span data-ttu-id="45565-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45565-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45565-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45565-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45565-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45565-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45565-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45565-119">E_FAIL</span></span>|<span data-ttu-id="45565-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45565-121">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45565-121">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45565-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45565-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45565-123">설명</span><span class="sxs-lookup"><span data-stu-id="45565-123">Remarks</span></span>  

 <span data-ttu-id="45565-124">`EndCustomDump`메서드는 메서드에 대 한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지우고 `BeginCustomDump` 연결 된 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="45565-124">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="45565-125">사용자 지정 스택 덤프가 완료 된 후이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45565-125">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="45565-126">호출 하지 못하면 `EndCustomDump` 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="45565-126">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45565-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45565-127">Requirements</span></span>  

 <span data-ttu-id="45565-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45565-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45565-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="45565-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45565-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45565-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45565-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45565-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45565-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45565-132">See also</span></span>

- [<span data-ttu-id="45565-133">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="45565-133">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="45565-134">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="45565-134">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="45565-135">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45565-135">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
