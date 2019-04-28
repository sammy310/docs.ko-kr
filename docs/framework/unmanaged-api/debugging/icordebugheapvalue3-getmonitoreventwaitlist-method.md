---
title: ICorDebugHeapValue3::GetMonitorEventWaitList 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db331d75244d59aacf2207a6b83a3f337a64b989
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700962"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="1ccb8-102">ICorDebugHeapValue3::GetMonitorEventWaitList 메서드</span><span class="sxs-lookup"><span data-stu-id="1ccb8-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="1ccb8-103">모니터 잠금과 사용 하 여 연결 된 이벤트에 대 한 큐에 대기 중인 스레드는 정렬 된 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ccb8-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ccb8-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ccb8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ccb8-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="1ccb8-106">[out] 스레드 순서 있는 목록을 제공 하는 ICorDebugThreadEnum 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ccb8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ccb8-107">Return Value</span></span>  
 <span data-ttu-id="1ccb8-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1ccb8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ccb8-109">HRESULT</span></span>|<span data-ttu-id="1ccb8-110">설명</span><span class="sxs-lookup"><span data-stu-id="1ccb8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ccb8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ccb8-111">S_OK</span></span>|<span data-ttu-id="1ccb8-112">The list is not empty.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-112">The list is not empty.</span></span>|  
|<span data-ttu-id="1ccb8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1ccb8-113">S_FALSE</span></span>|<span data-ttu-id="1ccb8-114">목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="1ccb8-115">예외</span><span class="sxs-lookup"><span data-stu-id="1ccb8-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ccb8-116">설명</span><span class="sxs-lookup"><span data-stu-id="1ccb8-116">Remarks</span></span>  
 <span data-ttu-id="1ccb8-117">목록의 첫 번째 스레드는 다음 호출에 의해 제공 되는 첫 번째 스레드가 <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1ccb8-118">목록에서 다음 스레드에서 다음 호출 등에 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="1ccb8-119">목록에 비어 있지 않으면이 메서드는 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="1ccb8-120">목록이 비어 있으면 반환 S_FALSE; 이 경우는 열거형은 비어 있더라도 여전히 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="1ccb8-121">두 경우 모두 열거형 인터페이스는 현재 동기화 된 상태의 기간에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="1ccb8-122">그러나 스레드의 인터페이스에서 분배는 스레드가 종료 될 때까지 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="1ccb8-123">경우 `ppThreadEnum` 유효한 포인터가 아닙니다 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="1ccb8-124">확인할 수 없는 모니터에 대 한 대기 중인 스레드가 있으면 하는 것과 같은 오류가 발생 하는 경우 메서드는 오류를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ccb8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ccb8-125">Requirements</span></span>  
 <span data-ttu-id="1ccb8-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ccb8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ccb8-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ccb8-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ccb8-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ccb8-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ccb8-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ccb8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccb8-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ccb8-130">See also</span></span>

- [<span data-ttu-id="1ccb8-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ccb8-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1ccb8-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="1ccb8-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
