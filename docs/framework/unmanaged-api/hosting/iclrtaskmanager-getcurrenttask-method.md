---
title: ICLRTaskManager::GetCurrentTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: 9cb97d9f383b7b54b431457042c4c4a7fc9cd876
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762834"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="4980c-102">ICLRTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="4980c-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="4980c-103">메서드 호출이 시작 된 운영 체제 스레드에서 현재 실행 중인 [ICLRTask](iclrtask-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4980c-104">구문</span><span class="sxs-lookup"><span data-stu-id="4980c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4980c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4980c-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="4980c-106">제한이 호출이 시작 된 운영 체제 스레드에서 현재 실행 중인 인스턴스의 주소에 대 한 포인터 `ICLRTask` 이거나,이 스레드에서 현재 실행 중인 작업이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4980c-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="4980c-107">Return Value</span></span>  
  
|<span data-ttu-id="4980c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4980c-108">HRESULT</span></span>|<span data-ttu-id="4980c-109">Description</span><span class="sxs-lookup"><span data-stu-id="4980c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4980c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4980c-110">S_OK</span></span>|<span data-ttu-id="4980c-111">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="4980c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4980c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4980c-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4980c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4980c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4980c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-115">The call timed out.</span></span>|  
|<span data-ttu-id="4980c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4980c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4980c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4980c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4980c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4980c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4980c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4980c-120">E_FAIL</span></span>|<span data-ttu-id="4980c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4980c-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4980c-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4980c-124">설명</span><span class="sxs-lookup"><span data-stu-id="4980c-124">Remarks</span></span>  
 <span data-ttu-id="4980c-125">`ICLRTask` `ppTask` 매개 변수가 가리키는 인스턴스로, CLR에 대해 현재 실행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="4980c-126">`ICLRTask`인스턴스는 호스트의 작업을 나타내는 해당 [IHostTask](ihosttask-interface.md) 인스턴스와 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4980c-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4980c-127">Requirements</span></span>  
 <span data-ttu-id="4980c-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4980c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4980c-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4980c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4980c-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4980c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4980c-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4980c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4980c-132">참조</span><span class="sxs-lookup"><span data-stu-id="4980c-132">See also</span></span>

- [<span data-ttu-id="4980c-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4980c-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4980c-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4980c-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4980c-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4980c-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4980c-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4980c-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
