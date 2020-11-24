---
title: ICorProfilerCallback::RemotingServerInvocationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
ms.openlocfilehash: 630efefde2a90eca0b40643ea8d7ffe08efdc763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676831"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="ccef8-102">ICorProfilerCallback::RemotingServerInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="ccef8-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>

<span data-ttu-id="ccef8-103">프로세스가 원격 메서드 호출 요청에 대 한 응답으로 메서드를 호출 하 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ccef8-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccef8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccef8-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="ccef8-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccef8-105">Requirements</span></span>  

 <span data-ttu-id="ccef8-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccef8-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccef8-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccef8-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccef8-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccef8-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccef8-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccef8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccef8-110">참조</span><span class="sxs-lookup"><span data-stu-id="ccef8-110">See also</span></span>

- [<span data-ttu-id="ccef8-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccef8-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
