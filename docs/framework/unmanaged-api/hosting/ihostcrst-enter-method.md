---
title: IHostCrst::Enter 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124439"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="4ba17-102">IHostCrst::Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="4ba17-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="4ba17-103">현재 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스로 표시 되는 임계 영역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba17-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ba17-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ba17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ba17-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="4ba17-106">진행 작업이 차단 될 경우 호스트에서 수행할 동작을 나타내는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ba17-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4ba17-107">Return Value</span></span>  
  
|<span data-ttu-id="4ba17-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ba17-108">HRESULT</span></span>|<span data-ttu-id="4ba17-109">설명</span><span class="sxs-lookup"><span data-stu-id="4ba17-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ba17-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ba17-110">S_OK</span></span>|<span data-ttu-id="4ba17-111">`Enter` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="4ba17-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ba17-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ba17-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ba17-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ba17-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ba17-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-115">The call timed out.</span></span>|  
|<span data-ttu-id="4ba17-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ba17-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ba17-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ba17-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ba17-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ba17-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ba17-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ba17-120">E_FAIL</span></span>|<span data-ttu-id="4ba17-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ba17-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ba17-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ba17-124">주의</span><span class="sxs-lookup"><span data-stu-id="4ba17-124">Remarks</span></span>  
 <span data-ttu-id="4ba17-125">`Enter`는 Win32 `EnterCriticalSection` 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ba17-126">이 메서드는 임계 영역을 입력할 때까지 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba17-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ba17-127">Requirements</span></span>  
 <span data-ttu-id="4ba17-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ba17-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba17-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4ba17-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ba17-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba17-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ba17-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba17-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba17-132">참조</span><span class="sxs-lookup"><span data-stu-id="4ba17-132">See also</span></span>

- [<span data-ttu-id="4ba17-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ba17-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4ba17-134">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ba17-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="4ba17-135">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ba17-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
