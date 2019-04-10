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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83c9a4aa165057f1345de2c6f5bda80e4317d06c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221810"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="21def-102">ICorProfilerCallback::RemotingServerInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="21def-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="21def-103">프로세스에서 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="21def-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21def-104">구문</span><span class="sxs-lookup"><span data-stu-id="21def-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="21def-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21def-105">Requirements</span></span>  
 <span data-ttu-id="21def-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21def-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21def-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21def-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21def-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21def-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="21def-109">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="21def-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="21def-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="21def-110">See also</span></span>

- [<span data-ttu-id="21def-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21def-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
