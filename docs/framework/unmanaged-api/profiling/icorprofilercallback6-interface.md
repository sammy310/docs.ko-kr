---
title: ICorProfilerCallback6 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864871"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="353a4-102">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="353a4-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="353a4-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="353a4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="353a4-104">공용 언어 런타임에서 어셈블리를 로드 하 고 있음을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="353a4-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="353a4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="353a4-105">Methods</span></span>  
  
|<span data-ttu-id="353a4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="353a4-106">Method</span></span>|<span data-ttu-id="353a4-107">설명</span><span class="sxs-lookup"><span data-stu-id="353a4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="353a4-108">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="353a4-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="353a4-109">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="353a4-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="353a4-110">주의</span><span class="sxs-lookup"><span data-stu-id="353a4-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="353a4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="353a4-111">Requirements</span></span>  
 <span data-ttu-id="353a4-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="353a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="353a4-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="353a4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="353a4-114">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="353a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353a4-115">참조</span><span class="sxs-lookup"><span data-stu-id="353a4-115">See also</span></span>

- [<span data-ttu-id="353a4-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="353a4-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
