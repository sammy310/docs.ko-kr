---
description: '자세히 알아보기: ICorProfilerCallback10:: EventPipeProviderCreated 메서드'
title: 'ICorProfilerCallback10:: EventPipeProviderCreated 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeProviderCreated
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4602438148a369f2a2321a2ec2e959cc375e37cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805586"
---
# <a name="icorprofilercallback10eventpipeprovidercreated-method"></a><span data-ttu-id="10da9-103">ICorProfilerCallback10:: EventPipeProviderCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="10da9-103">ICorProfilerCallback10::EventPipeProviderCreated Method</span></span>

<span data-ttu-id="10da9-104">EventPipe 공급자가 만들어질 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="10da9-104">Notifies the profiler whenever an EventPipe provider is created.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="10da9-105">구문</span><span class="sxs-lookup"><span data-stu-id="10da9-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeProviderCreated([in] EVENTPIPE_PROVIDER provider); 
```  
  
## <a name="parameters"></a><span data-ttu-id="10da9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10da9-106">Parameters</span></span>

<span data-ttu-id="10da9-107">`provider` 진행 만든 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="10da9-107">`provider` [in] The provider that was created.</span></span>

## <a name="requirements"></a><span data-ttu-id="10da9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10da9-108">Requirements</span></span>  

<span data-ttu-id="10da9-109">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10da9-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="10da9-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10da9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="10da9-111">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10da9-111">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10da9-112">참조</span><span class="sxs-lookup"><span data-stu-id="10da9-112">See also</span></span>

- [<span data-ttu-id="10da9-113">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10da9-113">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="10da9-114">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10da9-114">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="10da9-115">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10da9-115">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="10da9-116">ICorProfilerInfo12 EventPipeAddProviderToSession 메서드</span><span class="sxs-lookup"><span data-stu-id="10da9-116">ICorProfilerInfo12.EventPipeAddProviderToSession Method</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
