---
description: '자세히 알아보기: ICorProfilerCallback:: RemotingClientInvocationStarted 메서드'
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
ms.openlocfilehash: 3727383c3a23fa9e4327970e84c6ebde4ab14db0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788971"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="cfa79-103">ICorProfilerCallback::RemotingClientInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="cfa79-103">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>

<span data-ttu-id="cfa79-104">원격 호출이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-104">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa79-105">구문</span><span class="sxs-lookup"><span data-stu-id="cfa79-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cfa79-106">설명</span><span class="sxs-lookup"><span data-stu-id="cfa79-106">Remarks</span></span>  

 <span data-ttu-id="cfa79-107">이 이벤트는 동기 및 비동기 호출에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-107">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="cfa79-108">다음 콜백 쌍은 모두 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-108">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="cfa79-109">`RemotingClientInvocationStarted` 및 [ICorProfilerCallback:: Remo Clientsendingmessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfa79-109">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="cfa79-110">[ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) 및 [ICorProfilerCallback:: RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfa79-110">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="cfa79-111">[ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) 및 [ICorProfilerCallback:: Remo Serversendingreply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfa79-111">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="cfa79-112">원격 콜백과 관련 하 여 다음과 같은 문제를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-112">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="cfa79-113">원격 함수 실행은 프로파일러 API에 반영 되지 않으므로 클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림이 제대로 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-113">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="cfa79-114">실제 호출은 프록시 개체를 통해 수행 됩니다. 프로파일러에는 특정 함수가 JIT 컴파일되지만 사용 되지 않는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-114">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="cfa79-115">프로파일러는 비동기 원격 이벤트에 대 한 정확한 알림을 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfa79-115">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa79-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfa79-116">Requirements</span></span>  

 <span data-ttu-id="cfa79-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfa79-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa79-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfa79-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cfa79-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfa79-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfa79-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa79-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa79-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfa79-121">See also</span></span>

- [<span data-ttu-id="cfa79-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfa79-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
