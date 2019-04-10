---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178635"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="11e25-102">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11e25-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="11e25-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="11e25-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="11e25-104">공용 언어 런타임이 메모리 내 모듈과 연관된 기호 스트림이 업데이트되었음을 프로파일러에 알리기 위해 사용하는 콜백 메서드를 제공하는 [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) 의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="11e25-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11e25-105">메서드</span><span class="sxs-lookup"><span data-stu-id="11e25-105">Methods</span></span>  
  
|<span data-ttu-id="11e25-106">메서드</span><span class="sxs-lookup"><span data-stu-id="11e25-106">Method</span></span>|<span data-ttu-id="11e25-107">설명</span><span class="sxs-lookup"><span data-stu-id="11e25-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11e25-108">ModuleInMemorySymbolsUpdated 메서드</span><span class="sxs-lookup"><span data-stu-id="11e25-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="11e25-109">메모리 내 모듈과 연관된 기호 스트림이 업데이트되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="11e25-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11e25-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11e25-110">Requirements</span></span>  
 <span data-ttu-id="11e25-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e25-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11e25-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11e25-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="11e25-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="11e25-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11e25-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="11e25-114">See also</span></span>

- [<span data-ttu-id="11e25-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11e25-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
