---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeStopSession 메서드'
title: 'ICorProfilerInfo12:: EventPipeStopSession 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeStopSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c1b104f63755bcec52a113be7e2aa9af76ecd34e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805716"
---
# <a name="icorprofilerinfo12eventpipestopsession-method"></a><span data-ttu-id="7fa09-103">ICorProfilerInfo12:: EventPipeStopSession 메서드</span><span class="sxs-lookup"><span data-stu-id="7fa09-103">ICorProfilerInfo12::EventPipeStopSession Method</span></span>

<span data-ttu-id="7fa09-104">EventPipe 세션을 중지 하 여 이후 이벤트가 세션에 기록 되는 것을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa09-104">Stops an EventPipe session, preventing any future events from being written to the session.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7fa09-105">구문</span><span class="sxs-lookup"><span data-stu-id="7fa09-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeStopSession(
        [in] EVENTPIPE_SESSION session);
```  
  
## <a name="parameters"></a><span data-ttu-id="7fa09-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fa09-106">Parameters</span></span>

<span data-ttu-id="7fa09-107">`session` 진행 중지할 세션의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa09-107">`session` [in] The ID of the session to stop.</span></span>

## <a name="requirements"></a><span data-ttu-id="7fa09-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fa09-108">Requirements</span></span>  

<span data-ttu-id="7fa09-109">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fa09-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="7fa09-110">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fa09-110">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7fa09-111">참조</span><span class="sxs-lookup"><span data-stu-id="7fa09-111">See also</span></span>

- [<span data-ttu-id="7fa09-112">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fa09-112">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7fa09-113">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fa09-113">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="7fa09-114">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fa09-114">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
