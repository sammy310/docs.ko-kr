---
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
ms.openlocfilehash: 11515bbb5717222a0030c1953b4eab4eb1b83bb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731646"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="cad64-102">IHostTaskManager::EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="cad64-102">IHostTaskManager::EnterRuntime Method</span></span>

<span data-ttu-id="cad64-103">플랫폼 호출 메서드와 같은 관리 되지 않는 메서드에 대 한 호출이 CLR (공용 언어 런타임)에 실행 제어를 반환 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad64-104">구문</span><span class="sxs-lookup"><span data-stu-id="cad64-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cad64-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="cad64-105">Return Value</span></span>  
  
|<span data-ttu-id="cad64-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cad64-106">HRESULT</span></span>|<span data-ttu-id="cad64-107">설명</span><span class="sxs-lookup"><span data-stu-id="cad64-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cad64-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="cad64-108">S_OK</span></span>|<span data-ttu-id="cad64-109">`EnterRuntime` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="cad64-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cad64-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cad64-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cad64-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cad64-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cad64-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-113">The call timed out.</span></span>|  
|<span data-ttu-id="cad64-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cad64-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cad64-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cad64-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cad64-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cad64-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cad64-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cad64-118">E_FAIL</span></span>|<span data-ttu-id="cad64-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cad64-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cad64-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cad64-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cad64-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cad64-123">메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cad64-124">설명</span><span class="sxs-lookup"><span data-stu-id="cad64-124">Remarks</span></span>  

 <span data-ttu-id="cad64-125">`EnterRuntime` 는 [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) 메서드에 대 한 이전 호출이 수행 되었고 실행이 완료 되었으며 런타임에 실행 제어를 반환 하는 관리 되지 않는 함수를 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cad64-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) 는 이전에를 호출 하는 관리 되지 않는 함수가 `LeaveRuntime` 관리 코드를 호출 하 고 있음을 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cad64-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cad64-127">Requirements</span></span>  

 <span data-ttu-id="cad64-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cad64-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cad64-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cad64-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cad64-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cad64-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cad64-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cad64-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad64-132">참조</span><span class="sxs-lookup"><span data-stu-id="cad64-132">See also</span></span>

- <span data-ttu-id="cad64-133">[고급 COM 상호 운용성](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cad64-133">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="cad64-134">방법: PInvoke를 사용 하 여 관리 코드에서 네이티브 Dll 호출</span><span class="sxs-lookup"><span data-stu-id="cad64-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="cad64-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cad64-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cad64-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cad64-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cad64-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cad64-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="cad64-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cad64-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="cad64-139">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="cad64-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
