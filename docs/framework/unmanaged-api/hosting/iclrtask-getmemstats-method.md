---
description: '다음에 대 한 자세한 정보: ICLRTask:: GetMemStats 메서드'
title: ICLRTask::GetMemStats 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: ed81e9ced20a43528247d70012077ffd466f9ed1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784979"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="10330-103">ICLRTask::GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="10330-103">ICLRTask::GetMemStats Method</span></span>

<span data-ttu-id="10330-104">현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업과 관련 된 통계 메모리 사용 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10330-104">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10330-105">구문</span><span class="sxs-lookup"><span data-stu-id="10330-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10330-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10330-106">Parameters</span></span>  

 `pMemUsage`  
 <span data-ttu-id="10330-107">제한이 할당 된 바이트 수를 포함 하 여 태스크의 메모리 사용에 대 한 세부 정보를 포함 하는 [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="10330-107">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10330-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="10330-108">Return Value</span></span>  
  
|<span data-ttu-id="10330-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10330-109">HRESULT</span></span>|<span data-ttu-id="10330-110">설명</span><span class="sxs-lookup"><span data-stu-id="10330-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10330-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="10330-111">S_OK</span></span>|<span data-ttu-id="10330-112">`GetMemStats` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-112">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="10330-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10330-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10330-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10330-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10330-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10330-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-116">The call timed out.</span></span>|  
|<span data-ttu-id="10330-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10330-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10330-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10330-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10330-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10330-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10330-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10330-121">E_FAIL</span></span>|<span data-ttu-id="10330-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10330-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10330-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10330-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10330-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10330-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10330-125">Requirements</span></span>  

 <span data-ttu-id="10330-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10330-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10330-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="10330-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10330-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10330-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10330-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10330-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10330-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10330-130">See also</span></span>

- [<span data-ttu-id="10330-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10330-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="10330-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10330-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="10330-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10330-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="10330-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10330-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
