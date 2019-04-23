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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2722497db5622dee4adcfd9381837477b89a8f63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206579"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="c5a01-102">ICorProfilerCallback::RemotingClientInvocationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c5a01-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="c5a01-103">클라이언트에서 원격 호출이 완료 될 때까지 실행 된 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a01-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5a01-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5a01-105">설명</span><span class="sxs-lookup"><span data-stu-id="c5a01-105">Remarks</span></span>  
 <span data-ttu-id="c5a01-106">동기 원격 호출 되었으면 서버에서 완료 될 때까지 실행할 수도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="c5a01-107">원격 호출이 비동기 인 경우 회신을 여전히 예상 되는 호출 처리 될 때입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="c5a01-108">에 대 한 호출으로 발생 하는 응답을 예상 되 면 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 추가로 호출 하 고 `RemotingClientInvocationFinished` 필요한 보조 처리 하는 비동기 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="c5a01-109">각 콜백의 다음 쌍 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="c5a01-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="c5a01-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="c5a01-111">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 고 [icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="c5a01-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="c5a01-112">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 고 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="c5a01-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="c5a01-113">원격 콜백 사용 하 여 다음 문제를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="c5a01-114">클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림을 올바르게 수신 되지 않습니다 있도록 remoting 함수 실행 API 프로파일러에 의해 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="c5a01-115">프록시 개체를 통해 발생 하는 실제 호출 프로파일러, 특정 함수는 JIT 컴파일 되었지만 사용 되지는 않습니다 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="c5a01-116">프로파일러는 비동기 원격 서비스 이벤트에 대 한 정확한 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a01-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a01-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5a01-117">Requirements</span></span>  
 <span data-ttu-id="c5a01-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5a01-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a01-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5a01-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5a01-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5a01-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5a01-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5a01-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a01-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5a01-122">See also</span></span>

- [<span data-ttu-id="c5a01-123">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5a01-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
