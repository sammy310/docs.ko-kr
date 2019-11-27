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
ms.openlocfilehash: ccb970fb2eb387f1be795f9322d5bf9650593a35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445772"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="1af7f-102">ICorProfilerCallback::RemotingServerInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="1af7f-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="1af7f-103">프로세스가 원격 메서드 호출 요청에 대 한 응답으로 메서드를 호출 하 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1af7f-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af7f-104">구문</span><span class="sxs-lookup"><span data-stu-id="1af7f-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1af7f-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1af7f-105">Requirements</span></span>  
 <span data-ttu-id="1af7f-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1af7f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af7f-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1af7f-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1af7f-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af7f-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af7f-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af7f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af7f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1af7f-110">See also</span></span>

- [<span data-ttu-id="1af7f-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1af7f-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
