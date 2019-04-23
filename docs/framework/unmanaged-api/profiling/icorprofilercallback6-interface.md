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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077240"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="fa0d5-102">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa0d5-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="fa0d5-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="fa0d5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fa0d5-104">서브 클래스 [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) 공용 언어 런타임 어셈블리를 로드 하는 프로파일러에 알리기 위해 사용 하는 콜백 메서드를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0d5-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa0d5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fa0d5-105">Methods</span></span>  
  
|<span data-ttu-id="fa0d5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fa0d5-106">Method</span></span>|<span data-ttu-id="fa0d5-107">설명</span><span class="sxs-lookup"><span data-stu-id="fa0d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa0d5-108">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="fa0d5-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="fa0d5-109">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fa0d5-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa0d5-110">설명</span><span class="sxs-lookup"><span data-stu-id="fa0d5-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0d5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa0d5-111">Requirements</span></span>  
 <span data-ttu-id="fa0d5-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa0d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0d5-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa0d5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa0d5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0d5-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa0d5-115">See also</span></span>

- [<span data-ttu-id="fa0d5-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa0d5-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
