---
description: '자세히 알아보기: ICorProfilerCallback:: RemotingServerSendingReply 메서드'
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
ms.openlocfilehash: 236a707fcbc051a3d00c408f71f3b4f9f452c220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788880"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="cb77a-103">ICorProfilerCallback::RemotingServerSendingReply 메서드</span><span class="sxs-lookup"><span data-stu-id="cb77a-103">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>

<span data-ttu-id="cb77a-104">프로세스가 원격 메서드 호출 요청 처리를 완료 했으며 채널을 통해 회신을 전송 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-104">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb77a-105">구문</span><span class="sxs-lookup"><span data-stu-id="cb77a-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb77a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb77a-106">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="cb77a-107">진행 다음 조건에서 [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) 에 제공 된 값과 일치 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-107">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="cb77a-108">원격 GUID 쿠키가 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-108">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="cb77a-109">채널에서 메시지를 전송 하는 데 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-109">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="cb77a-110">GUID 쿠키는 클라이언트 쪽 프로세스에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-110">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="cb77a-111">이렇게 하면 원격 호출을 쉽게 페어링 하 고 논리 호출 스택을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb77a-111">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="cb77a-112">진행 `true` 호출이 비동기 이면이 고, 그렇지 않으면 인 값입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="cb77a-112">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb77a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb77a-113">Requirements</span></span>  

 <span data-ttu-id="cb77a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb77a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb77a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb77a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb77a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb77a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb77a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb77a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb77a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb77a-118">See also</span></span>

- [<span data-ttu-id="cb77a-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb77a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
