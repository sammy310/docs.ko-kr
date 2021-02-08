---
description: '자세히 알아보기: ICorProfilerCallback6 인터페이스'
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
ms.openlocfilehash: 12eaafff8bd9ab8d4d58eac8f2d62415531bc898
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781755"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="3feac-103">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3feac-103">ICorProfilerCallback6 Interface</span></span>

<span data-ttu-id="3feac-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="3feac-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3feac-105">공용 언어 런타임에서 어셈블리를 로드 하 고 있음을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3feac-105">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3feac-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3feac-106">Methods</span></span>  
  
|<span data-ttu-id="3feac-107">메서드</span><span class="sxs-lookup"><span data-stu-id="3feac-107">Method</span></span>|<span data-ttu-id="3feac-108">설명</span><span class="sxs-lookup"><span data-stu-id="3feac-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3feac-109">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3feac-109">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="3feac-110">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3feac-110">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3feac-111">설명</span><span class="sxs-lookup"><span data-stu-id="3feac-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3feac-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3feac-112">Requirements</span></span>  

 <span data-ttu-id="3feac-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3feac-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3feac-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3feac-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3feac-115">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3feac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3feac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3feac-116">See also</span></span>

- [<span data-ttu-id="3feac-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3feac-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
