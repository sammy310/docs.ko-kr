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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4ef2971d9835070e9db72a5e5d370ff35c8edfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106441"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="338d8-102">IHostTaskManager::EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="338d8-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="338d8-103">관리 되지 않는 메서드를 호출 메서드를 호출 하는 플랫폼와 같은 실행 결과 제어가 반환 되는 CLR (공용 언어 런타임) 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="338d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="338d8-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="338d8-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="338d8-105">Return Value</span></span>  
  
|<span data-ttu-id="338d8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="338d8-106">HRESULT</span></span>|<span data-ttu-id="338d8-107">설명</span><span class="sxs-lookup"><span data-stu-id="338d8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="338d8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="338d8-108">S_OK</span></span>|`EnterRuntime` <span data-ttu-id="338d8-109">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-109">returned successfully.</span></span>|  
|<span data-ttu-id="338d8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="338d8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="338d8-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="338d8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="338d8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="338d8-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-113">The call timed out.</span></span>|  
|<span data-ttu-id="338d8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="338d8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="338d8-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="338d8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="338d8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="338d8-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="338d8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="338d8-118">E_FAIL</span></span>|<span data-ttu-id="338d8-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="338d8-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="338d8-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="338d8-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="338d8-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="338d8-123">요청된 된 할당을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="338d8-124">설명</span><span class="sxs-lookup"><span data-stu-id="338d8-124">Remarks</span></span>  
 `EnterRuntime` <span data-ttu-id="338d8-125">호스트에 알리기 위해 호출 됩니다는는 관리 되지 않는 함수를 호출 하 여 이전를 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) 메서드 만들어진가 실행을 완료 하 고 런타임에 실행 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-125">is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="338d8-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) 호스트에 알리기 위해 호출 됩니다는는 관리 되지 않는 함수를 호출 하 여 이전 `LeaveRuntime` 만들어진, 관리 되는 코드로 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d8-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="338d8-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="338d8-127">Requirements</span></span>  
 <span data-ttu-id="338d8-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="338d8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="338d8-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="338d8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="338d8-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="338d8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="338d8-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="338d8-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="338d8-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="338d8-132">See also</span></span>

- [<span data-ttu-id="338d8-133">고급 수준의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="338d8-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="338d8-134">방법: PInvoke를 사용 하 여 관리 되는 코드에서 네이티브 Dll 호출</span><span class="sxs-lookup"><span data-stu-id="338d8-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="338d8-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="338d8-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="338d8-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="338d8-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="338d8-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="338d8-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="338d8-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="338d8-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="338d8-139">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="338d8-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
