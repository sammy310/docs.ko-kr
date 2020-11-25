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
ms.openlocfilehash: df0e66c8563404d7de4f1e11f41483f2f61f519c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721558"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="e9507-102">ICorProfilerInfo4::EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e9507-102">ICorProfilerInfo4::EnumThreads Method</span></span>

<span data-ttu-id="e9507-103">프로 파일링 된 프로세스에서 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9507-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9507-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9507-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9507-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9507-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="e9507-106">제한이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9507-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9507-107">설명</span><span class="sxs-lookup"><span data-stu-id="e9507-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9507-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9507-108">Requirements</span></span>  

 <span data-ttu-id="e9507-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9507-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9507-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9507-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9507-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9507-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9507-112">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9507-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9507-113">참조</span><span class="sxs-lookup"><span data-stu-id="e9507-113">See also</span></span>

- [<span data-ttu-id="e9507-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9507-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="e9507-115">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9507-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="e9507-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9507-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e9507-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="e9507-117">Profiling</span></span>](index.md)
