---
title: ICorProfilerCallback::RemotingServerSendingReply 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024b1f3f7e08dc21582789de7f3899e8e44d5e39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041836"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="df19b-102">ICorProfilerCallback::RemotingServerSendingReply 메서드</span><span class="sxs-lookup"><span data-stu-id="df19b-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="df19b-103">프로세스에서 원격 메서드 호출 요청 처리를 완료 하 고 채널을 통해 회신을 전송 하려고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df19b-104">구문</span><span class="sxs-lookup"><span data-stu-id="df19b-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df19b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df19b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="df19b-106">[in] 에 제공 된 값을 사용 하 여 해당 하는 GUID에 대 한 포인터 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 이러한 조건에서:</span><span class="sxs-lookup"><span data-stu-id="df19b-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="df19b-107">원격 GUID 쿠키 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="df19b-108">채널은 메시지 전송에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="df19b-109">GUID 쿠키는 클라이언트 쪽 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="df19b-110">따라서 쉽게 페어링 원격 호출 및 논리 호출 스택 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="df19b-111">[in] 값을 `true` 호출이 고, 그렇지 않으면 비동기 이면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="df19b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df19b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df19b-112">Requirements</span></span>  
 <span data-ttu-id="df19b-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="df19b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df19b-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df19b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df19b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df19b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df19b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df19b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df19b-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="df19b-117">See also</span></span>

- [<span data-ttu-id="df19b-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df19b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
