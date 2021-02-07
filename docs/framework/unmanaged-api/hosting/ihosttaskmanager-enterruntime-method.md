---
description: '자세히 알아보기: IHostTaskManager:: EnterRuntime 메서드'
title: IHostTaskManager::EnterRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 924fa18c9acbf02d8c614ffd9bf95657fd73ed14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753837"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="8e968-103">IHostTaskManager::EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="8e968-103">IHostTaskManager::EnterRuntime Method</span></span>

<span data-ttu-id="8e968-104">플랫폼 호출 메서드와 같은 관리 되지 않는 메서드에 대 한 호출이 CLR (공용 언어 런타임)에 실행 제어를 반환 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-104">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e968-105">구문</span><span class="sxs-lookup"><span data-stu-id="8e968-105">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e968-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="8e968-106">Return Value</span></span>  
  
|<span data-ttu-id="8e968-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e968-107">HRESULT</span></span>|<span data-ttu-id="8e968-108">설명</span><span class="sxs-lookup"><span data-stu-id="8e968-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e968-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e968-109">S_OK</span></span>|<span data-ttu-id="8e968-110">`EnterRuntime` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-110">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="8e968-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e968-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e968-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e968-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e968-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e968-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-114">The call timed out.</span></span>|  
|<span data-ttu-id="8e968-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e968-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e968-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e968-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e968-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e968-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e968-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e968-119">E_FAIL</span></span>|<span data-ttu-id="8e968-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e968-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e968-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e968-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8e968-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8e968-124">메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-124">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e968-125">설명</span><span class="sxs-lookup"><span data-stu-id="8e968-125">Remarks</span></span>  

 <span data-ttu-id="8e968-126">`EnterRuntime` 는 [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) 메서드에 대 한 이전 호출이 수행 되었고 실행이 완료 되었으며 런타임에 실행 제어를 반환 하는 관리 되지 않는 함수를 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-126">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e968-127">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) 는 이전에를 호출 하는 관리 되지 않는 함수가 `LeaveRuntime` 관리 코드를 호출 하 고 있음을 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-127">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e968-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e968-128">Requirements</span></span>  

 <span data-ttu-id="8e968-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e968-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e968-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8e968-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e968-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e968-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e968-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e968-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e968-133">참조</span><span class="sxs-lookup"><span data-stu-id="8e968-133">See also</span></span>

- <span data-ttu-id="8e968-134">[고급 COM 상호 운용성](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8e968-134">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="8e968-135">방법: PInvoke를 사용 하 여 관리 코드에서 네이티브 Dll 호출</span><span class="sxs-lookup"><span data-stu-id="8e968-135">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="8e968-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e968-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8e968-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e968-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8e968-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e968-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8e968-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e968-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="8e968-140">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="8e968-140">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
