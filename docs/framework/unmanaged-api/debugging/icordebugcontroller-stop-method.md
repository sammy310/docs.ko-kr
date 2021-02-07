---
description: '자세히 알아보기: ICorDebugController:: Stop 메서드'
title: ICorDebugController::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 613fd81a03114580ae3d826a94d855023895b694
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764608"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="34711-103">ICorDebugController::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="34711-103">ICorDebugController::Stop Method</span></span>

<span data-ttu-id="34711-104">프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34711-104">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34711-105">구문</span><span class="sxs-lookup"><span data-stu-id="34711-105">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34711-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34711-106">Parameters</span></span>  

 `dwTimeoutIgnored`  
 <span data-ttu-id="34711-107">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34711-107">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34711-108">설명</span><span class="sxs-lookup"><span data-stu-id="34711-108">Remarks</span></span>  

 <span data-ttu-id="34711-109">`Stop` 프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34711-109">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="34711-110">관리 전용 디버깅 세션 중에는 관리 되지 않는 스레드가 계속 실행 될 수 있지만 관리 코드를 호출 하려고 하면 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-110">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="34711-111">Interop 디버깅 세션 중에는 관리 되지 않는 스레드도 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-111">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="34711-112">`dwTimeoutIgnored`값은 현재 무시 되 고 무한 (-1)으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-112">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="34711-113">교착 상태가 발생 하 여 협조적 중지가 실패 하면 모든 스레드가 일시 중단 되 고 E_TIMEOUT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-113">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34711-114">`Stop` 는 디버깅 API의 유일한 동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="34711-114">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="34711-115">`Stop`에서 S_OK를 반환할 때 프로세스가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-115">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="34711-116">수신기에 중지를 알리기 위한 콜백이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34711-116">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="34711-117">디버거는 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 를 호출 하 여 프로세스를 다시 시작할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34711-117">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="34711-118">디버거는 중지 카운터를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="34711-118">The debugger maintains a stop counter.</span></span> <span data-ttu-id="34711-119">카운터가 0으로 이동 하면 컨트롤러가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34711-119">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="34711-120">`Stop`또는 디스패치 된 각 콜백에 대 한 각 호출은 카운터를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="34711-120">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="34711-121">를 호출할 때마다 `ICorDebugController::Continue` 카운터가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="34711-121">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34711-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34711-122">Requirements</span></span>  

 <span data-ttu-id="34711-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34711-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34711-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34711-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34711-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34711-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34711-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34711-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34711-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34711-127">See also</span></span>
