---
title: ICorProfilerCallback::RemotingClientInvocationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
ms.openlocfilehash: 5de291774f1e20b4c399c416f9f52657fa8a9a84
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445817"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="e7d33-102">ICorProfilerCallback::RemotingClientInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e7d33-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="e7d33-103">Notifies the profiler that a remoting call has started.</span><span class="sxs-lookup"><span data-stu-id="e7d33-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d33-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7d33-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e7d33-105">주의</span><span class="sxs-lookup"><span data-stu-id="e7d33-105">Remarks</span></span>  
 <span data-ttu-id="e7d33-106">This event is the same for synchronous and asynchronous calls.</span><span class="sxs-lookup"><span data-stu-id="e7d33-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="e7d33-107">Each of the following pairs of callbacks will occur on the same thread:</span><span class="sxs-lookup"><span data-stu-id="e7d33-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="e7d33-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="e7d33-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="e7d33-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="e7d33-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="e7d33-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="e7d33-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="e7d33-111">You should be aware of the following issues with the remoting callbacks:</span><span class="sxs-lookup"><span data-stu-id="e7d33-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="e7d33-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span><span class="sxs-lookup"><span data-stu-id="e7d33-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="e7d33-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span><span class="sxs-lookup"><span data-stu-id="e7d33-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="e7d33-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span><span class="sxs-lookup"><span data-stu-id="e7d33-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d33-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7d33-115">Requirements</span></span>  
 <span data-ttu-id="e7d33-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7d33-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d33-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7d33-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7d33-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7d33-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7d33-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7d33-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d33-120">참조</span><span class="sxs-lookup"><span data-stu-id="e7d33-120">See also</span></span>

- [<span data-ttu-id="e7d33-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7d33-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
