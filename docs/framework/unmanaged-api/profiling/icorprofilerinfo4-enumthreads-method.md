---
title: ICorProfilerInfo4::EnumThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d4cffc7c407db6acd15462e1e00769101e44b40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780864"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="f42b5-102">ICorProfilerInfo4::EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f42b5-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="f42b5-103">프로 파일링된 된 프로세스의 모든 관리 되는 스레드 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42b5-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f42b5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f42b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f42b5-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f42b5-106">[out] 에 대 한 포인터를 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f42b5-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f42b5-107">설명</span><span class="sxs-lookup"><span data-stu-id="f42b5-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f42b5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f42b5-108">Requirements</span></span>  
 <span data-ttu-id="f42b5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42b5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f42b5-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f42b5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f42b5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f42b5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f42b5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f42b5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42b5-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f42b5-113">See also</span></span>

- [<span data-ttu-id="f42b5-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f42b5-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f42b5-115">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f42b5-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f42b5-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f42b5-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f42b5-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f42b5-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
