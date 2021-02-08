---
description: '자세히 알아보기: ICorProfilerCallback7 인터페이스'
title: ICorProfilerCallback7 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: 3db402db221fca4487939f9817b20ec0c5207fc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781742"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="85690-103">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85690-103">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="85690-104">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="85690-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="85690-105">공용 언어 런타임이 메모리 내 모듈과 연관된 기호 스트림이 업데이트되었음을 프로파일러에 알리기 위해 사용하는 콜백 메서드를 제공하는 [ICorProfilerCallback6](icorprofilercallback6-interface.md) 의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="85690-105">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85690-106">메서드</span><span class="sxs-lookup"><span data-stu-id="85690-106">Methods</span></span>  
  
|<span data-ttu-id="85690-107">메서드</span><span class="sxs-lookup"><span data-stu-id="85690-107">Method</span></span>|<span data-ttu-id="85690-108">설명</span><span class="sxs-lookup"><span data-stu-id="85690-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85690-109">ModuleInMemorySymbolsUpdated 메서드</span><span class="sxs-lookup"><span data-stu-id="85690-109">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="85690-110">메모리 내 모듈과 연관된 기호 스트림이 업데이트되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="85690-110">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85690-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85690-111">Requirements</span></span>  

 <span data-ttu-id="85690-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85690-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85690-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85690-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85690-114">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85690-114">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85690-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85690-115">See also</span></span>

- [<span data-ttu-id="85690-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85690-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
