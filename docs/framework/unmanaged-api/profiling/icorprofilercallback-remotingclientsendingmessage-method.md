---
title: ICorProfilerCallback::RemotingClientSendingMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: ae9cb089ad6c0b0422063d3db413b97eb6ff1405
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445797"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="4a46b-102">ICorProfilerCallback::RemotingClientSendingMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="4a46b-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="4a46b-103">클라이언트에서 서버로 요청을 보내고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a46b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a46b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a46b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a46b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="4a46b-106">진행 다음 조건에서 [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) 에 제공 된 값에 해당 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="4a46b-107">원격 GUID 쿠키가 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="4a46b-108">채널에서 메시지를 전송 하는 데 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="4a46b-109">GUID 쿠키는 서버 쪽 프로세스에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="4a46b-110">이렇게 하면 원격 호출을 쉽게 페어링 하 고 논리 호출 스택을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="4a46b-111">진행 호출이 비동기 인 경우 `true` 하는 값입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a46b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a46b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a46b-112">Requirements</span></span>  
 <span data-ttu-id="4a46b-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a46b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a46b-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a46b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a46b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a46b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a46b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a46b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a46b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a46b-117">See also</span></span>

- [<span data-ttu-id="4a46b-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a46b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
