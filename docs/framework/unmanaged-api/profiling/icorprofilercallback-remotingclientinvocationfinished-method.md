---
title: ICorProfilerCallback::RemotingClientInvocationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: c9a750b941b29047206c98410d4b4673d1101a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445841"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="753e2-102">ICorProfilerCallback::RemotingClientInvocationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="753e2-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="753e2-103">클라이언트에서 원격 호출이 완료 될 때까지 실행 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="753e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="753e2-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="753e2-105">주의</span><span class="sxs-lookup"><span data-stu-id="753e2-105">Remarks</span></span>  
 <span data-ttu-id="753e2-106">원격 호출이 동기화 된 경우 서버에서 완료 될 때까지 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="753e2-107">원격 호출이 비동기 이면 호출이 처리 될 때 응답이 여전히 예상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="753e2-108">회신이 필요한 경우 [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 에 대 한 호출로 발생 하 고 비동기 호출의 필수 보조 처리를 나타내는 `RemotingClientInvocationFinished`에 대 한 추가 호출로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="753e2-109">다음 콜백 쌍은 모두 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="753e2-110">`RemotingClientInvocationStarted` 및 [ICorProfilerCallback:: Remo Clientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="753e2-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="753e2-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 및 [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="753e2-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="753e2-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 및 [ICorProfilerCallback:: Remo Serversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="753e2-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="753e2-113">원격 콜백과 관련 하 여 다음과 같은 문제를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="753e2-114">원격 함수 실행은 프로파일러 API에 반영 되지 않으므로 클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림이 제대로 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="753e2-115">실제 호출은 프록시 개체를 통해 수행 됩니다. 프로파일러에는 특정 함수가 JIT 컴파일되지만 사용 되지 않는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="753e2-116">프로파일러는 비동기 원격 이벤트에 대 한 정확한 알림을 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="753e2-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="753e2-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="753e2-117">Requirements</span></span>  
 <span data-ttu-id="753e2-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="753e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="753e2-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="753e2-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="753e2-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="753e2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="753e2-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="753e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753e2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="753e2-122">See also</span></span>

- [<span data-ttu-id="753e2-123">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="753e2-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
