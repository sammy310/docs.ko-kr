---
title: ICorProfilerCallback::RemotingServerInvocationReturned 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
ms.openlocfilehash: 354736061a2c50b7db16070c3d4ff9c2548d394d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499950"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="72801-102">ICorProfilerCallback::RemotingServerInvocationReturned 메서드</span><span class="sxs-lookup"><span data-stu-id="72801-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="72801-103">프로세스가 원격 메서드 호출 요청에 대 한 응답으로 메서드 호출을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72801-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72801-104">구문</span><span class="sxs-lookup"><span data-stu-id="72801-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="72801-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72801-105">Requirements</span></span>  
 <span data-ttu-id="72801-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72801-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72801-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72801-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72801-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72801-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72801-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72801-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72801-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72801-110">See also</span></span>

- [<span data-ttu-id="72801-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72801-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
