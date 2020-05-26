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
ms.openlocfilehash: 79afaac4dce1c4baa9802d81af90c425f5de7a08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804915"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="1b3ca-102">IHostCrst::Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="1b3ca-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="1b3ca-103">현재 [IHostCrst](ihostcrst-interface.md) 인스턴스로 표시 되는 임계 영역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b3ca-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b3ca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b3ca-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="1b3ca-106">진행 작업이 차단 될 경우 호스트가 수행할 동작을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b3ca-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1b3ca-107">Return Value</span></span>  
  
|<span data-ttu-id="1b3ca-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b3ca-108">HRESULT</span></span>|<span data-ttu-id="1b3ca-109">Description</span><span class="sxs-lookup"><span data-stu-id="1b3ca-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b3ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b3ca-110">S_OK</span></span>|<span data-ttu-id="1b3ca-111">`Enter`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="1b3ca-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b3ca-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b3ca-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b3ca-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b3ca-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b3ca-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-115">The call timed out.</span></span>|  
|<span data-ttu-id="1b3ca-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b3ca-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b3ca-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b3ca-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b3ca-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b3ca-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b3ca-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b3ca-120">E_FAIL</span></span>|<span data-ttu-id="1b3ca-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b3ca-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b3ca-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b3ca-124">설명</span><span class="sxs-lookup"><span data-stu-id="1b3ca-124">Remarks</span></span>  
 <span data-ttu-id="1b3ca-125">`Enter`Win32 함수를 미러링합니다 `EnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="1b3ca-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b3ca-126">이 메서드는 임계 영역을 입력할 때까지 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b3ca-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b3ca-127">Requirements</span></span>  
 <span data-ttu-id="1b3ca-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3ca-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1b3ca-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b3ca-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b3ca-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b3ca-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3ca-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3ca-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b3ca-132">See also</span></span>

- [<span data-ttu-id="1b3ca-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ca-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1b3ca-134">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ca-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="1b3ca-135">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b3ca-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
