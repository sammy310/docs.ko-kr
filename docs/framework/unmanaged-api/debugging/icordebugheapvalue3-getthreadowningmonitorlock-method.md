---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1678f1de7c23387f028348dadbc7b61e2cdc035c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701023"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="788fe-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock 메서드</span><span class="sxs-lookup"><span data-stu-id="788fe-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="788fe-103">이 개체의 모니터 잠금을 소유 하는 관리 되는 스레드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="788fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="788fe-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="788fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="788fe-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="788fe-106">[out] 이 개체의 모니터 잠금을 소유 하는 관리 되는 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="788fe-107">[out] 이 스레드가 소유 중인를 반환 하기 전에 잠금을 해제 해야 하는 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="788fe-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="788fe-108">Return Value</span></span>  
 <span data-ttu-id="788fe-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="788fe-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="788fe-110">HRESULT</span></span>|<span data-ttu-id="788fe-111">설명</span><span class="sxs-lookup"><span data-stu-id="788fe-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="788fe-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="788fe-112">S_OK</span></span>|<span data-ttu-id="788fe-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="788fe-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="788fe-114">S_FALSE</span></span>|<span data-ttu-id="788fe-115">이 개체에 대 한 모니터 잠금을 소유 하는 관리 되는 스레드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="788fe-116">예외</span><span class="sxs-lookup"><span data-stu-id="788fe-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="788fe-117">설명</span><span class="sxs-lookup"><span data-stu-id="788fe-117">Remarks</span></span>  
 <span data-ttu-id="788fe-118">이 개체의 모니터 잠금을 소유 하는 관리 되는 스레드:</span><span class="sxs-lookup"><span data-stu-id="788fe-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="788fe-119">메서드는 S_OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="788fe-120">Thread 개체 스레드가 종료 될 때까지 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="788fe-121">이 개체에 대 한 모니터 잠금을 소유 하는 관리 되는 스레드가 없는 경우 `ppThread` 및 `pAcquisitionCount` 변경 되지 메서드에서 S_FALSE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="788fe-122">하는 경우 `ppThread` 또는 `pAcquisitionCount` 유효한 포인터가 아닙니다 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="788fe-123">확인할 수 있는 스레드가이 개체에 대 한 모니터 잠금을 소유 하 고 있는 경우 오류가 발생 하는 경우 메서드는 실패를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="788fe-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788fe-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="788fe-124">Requirements</span></span>  
 <span data-ttu-id="788fe-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="788fe-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="788fe-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="788fe-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="788fe-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="788fe-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="788fe-128">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788fe-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788fe-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="788fe-129">See also</span></span>

- [<span data-ttu-id="788fe-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="788fe-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="788fe-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="788fe-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
