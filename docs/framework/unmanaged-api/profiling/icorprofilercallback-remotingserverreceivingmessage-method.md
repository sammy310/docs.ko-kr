---
title: ICorProfilerCallback::RemotingServerReceivingMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30015cc6cae935c43cdbfec1a6eeae5c703ef9f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103209"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="536b8-102">ICorProfilerCallback::RemotingServerReceivingMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="536b8-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="536b8-103">프로세스가 원격 메서드 호출 또는 정품 인증 요청을 받았는지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="536b8-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="536b8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="536b8-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="536b8-106">[in] 에 제공 된 값을 사용 하 여 해당 하는 값 [icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) 이러한 조건에서:</span><span class="sxs-lookup"><span data-stu-id="536b8-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="536b8-107">원격 GUID 쿠키 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="536b8-108">채널은 메시지 전송에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="536b8-109">GUID 쿠키는 클라이언트 쪽 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="536b8-110">따라서 쉽게 페어링 원격 호출 및 논리 호출 스택 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="536b8-111">[in] 값을 `true` 호출이 고, 그렇지 않으면 비동기 이면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="536b8-112">설명</span><span class="sxs-lookup"><span data-stu-id="536b8-112">Remarks</span></span>  
 <span data-ttu-id="536b8-113">메시지 요청 비동기 인 경우 임의의 스레드에서 요청을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536b8-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="536b8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="536b8-114">Requirements</span></span>  
 <span data-ttu-id="536b8-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="536b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="536b8-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="536b8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="536b8-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="536b8-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="536b8-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="536b8-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="536b8-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="536b8-119">See also</span></span>

- [<span data-ttu-id="536b8-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="536b8-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
