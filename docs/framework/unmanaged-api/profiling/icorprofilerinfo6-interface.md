---
title: ICorProfilerInfo6 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: b1d31012662964132f8b65f030a062ae39ded56e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130367"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="84a50-102">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84a50-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="84a50-103">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="84a50-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="84a50-104">지정 된 NGen 모듈에 정의 되어 있고 지정 된 메서드를 인라인 하는 모든 메서드에 대 한 열거자를 제공 하는 [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="84a50-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84a50-105">메서드</span><span class="sxs-lookup"><span data-stu-id="84a50-105">Methods</span></span>  
  
|<span data-ttu-id="84a50-106">메서드</span><span class="sxs-lookup"><span data-stu-id="84a50-106">Method</span></span>|<span data-ttu-id="84a50-107">설명</span><span class="sxs-lookup"><span data-stu-id="84a50-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84a50-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="84a50-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="84a50-109">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에서 인라인 된 모든 메서드에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a50-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84a50-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84a50-110">Requirements</span></span>  
 <span data-ttu-id="84a50-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a50-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a50-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84a50-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84a50-113">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a50-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a50-114">참조</span><span class="sxs-lookup"><span data-stu-id="84a50-114">See also</span></span>

- [<span data-ttu-id="84a50-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84a50-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
