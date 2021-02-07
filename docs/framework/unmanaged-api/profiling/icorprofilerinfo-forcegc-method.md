---
description: '자세히 알아보기: ICorProfilerInfo:: ForceGC 메서드'
title: ICorProfilerInfo::ForceGC 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: 1abed09450b72730a11a168223b6da05e9baf9be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737534"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="3010f-103">ICorProfilerInfo::ForceGC 메서드</span><span class="sxs-lookup"><span data-stu-id="3010f-103">ICorProfilerInfo::ForceGC Method</span></span>

<span data-ttu-id="3010f-104">CLR (공용 언어 런타임) 내에서 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3010f-104">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3010f-105">구문</span><span class="sxs-lookup"><span data-stu-id="3010f-105">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3010f-106">설명</span><span class="sxs-lookup"><span data-stu-id="3010f-106">Remarks</span></span>  

 <span data-ttu-id="3010f-107">`ForceGC`관리 코드를 실행 하지 않고 스택에 프로파일러 콜백이 없는 스레드에서만 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3010f-107">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="3010f-108">가장 편리한 구현은 신호를 받을 때를 호출 하는 프로파일러 내에 별도의 스레드를 만드는 것입니다 `ForceGC` .</span><span class="sxs-lookup"><span data-stu-id="3010f-108">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3010f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3010f-109">Requirements</span></span>  

 <span data-ttu-id="3010f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3010f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3010f-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3010f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3010f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3010f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3010f-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3010f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3010f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3010f-114">See also</span></span>

- [<span data-ttu-id="3010f-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3010f-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
