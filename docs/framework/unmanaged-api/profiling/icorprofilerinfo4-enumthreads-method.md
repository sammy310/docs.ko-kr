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
ms.openlocfilehash: d42c86a458661d3559f99235a6d5b208c82d1963
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502810"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="f6363-102">ICorProfilerInfo4::EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f6363-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="f6363-103">프로 파일링 된 프로세스에서 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6363-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6363-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6363-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6363-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6363-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f6363-106">제한이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f6363-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6363-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6363-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6363-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6363-108">Requirements</span></span>  
 <span data-ttu-id="f6363-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6363-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6363-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6363-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6363-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6363-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6363-112">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6363-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6363-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6363-113">See also</span></span>

- [<span data-ttu-id="f6363-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6363-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f6363-115">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6363-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f6363-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6363-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f6363-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f6363-117">Profiling</span></span>](index.md)
