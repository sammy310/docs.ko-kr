---
title: ICorProfilerCallback::RemotingClientReceivingReply 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175137"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="a14e0-102">ICorProfilerCallback::RemotingClientReceivingReply 메서드</span><span class="sxs-lookup"><span data-stu-id="a14e0-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="a14e0-103">원격 호출의 서버 측 부분이 완료되었고 클라이언트가 이제 응답을 수신하고 처리하려고 하는 프로파일러에 알린다.</span><span class="sxs-lookup"><span data-stu-id="a14e0-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a14e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a14e0-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="a14e0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a14e0-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="a14e0-106">【인】 ICorProfilerCallback에서 제공 하는 값에 해당 하는 [값::Remoting서버보낸다음](icorprofilercallback-remotingserversendingreply-method.md) 조건:</span><span class="sxs-lookup"><span data-stu-id="a14e0-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="a14e0-107">원격 GUID 쿠키가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14e0-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="a14e0-108">채널이 메시지를 전송하는 데 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="a14e0-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="a14e0-109">GUID 쿠키는 서버 측 프로세스에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a14e0-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="a14e0-110">이렇게 하면 원격 호출을 쉽게 페어링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14e0-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="a14e0-111">【인】 호출이 비동기인 `true` 경우값입니다. 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="a14e0-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a14e0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a14e0-112">Requirements</span></span>  
 <span data-ttu-id="a14e0-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a14e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a14e0-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a14e0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a14e0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a14e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a14e0-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a14e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14e0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a14e0-117">See also</span></span>

- [<span data-ttu-id="a14e0-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a14e0-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
