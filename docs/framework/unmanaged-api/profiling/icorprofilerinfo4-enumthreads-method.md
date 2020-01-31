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
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862219"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="fb9c0-102">ICorProfilerInfo4::EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="fb9c0-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="fb9c0-103">프로 파일링 된 프로세스에서 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9c0-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb9c0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb9c0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb9c0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fb9c0-106">제한이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb9c0-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb9c0-107">주의</span><span class="sxs-lookup"><span data-stu-id="fb9c0-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb9c0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb9c0-108">Requirements</span></span>  
 <span data-ttu-id="fb9c0-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb9c0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb9c0-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb9c0-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb9c0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb9c0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb9c0-112">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb9c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9c0-113">참조</span><span class="sxs-lookup"><span data-stu-id="fb9c0-113">See also</span></span>

- [<span data-ttu-id="fb9c0-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb9c0-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="fb9c0-115">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb9c0-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fb9c0-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb9c0-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fb9c0-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="fb9c0-117">Profiling</span></span>](index.md)
