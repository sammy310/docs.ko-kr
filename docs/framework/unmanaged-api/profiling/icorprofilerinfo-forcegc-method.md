---
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
ms.openlocfilehash: 9f97da4e68d4b76178198e91c3fb8f08b56dda7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448191"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="0aee1-102">ICorProfilerInfo::ForceGC 메서드</span><span class="sxs-lookup"><span data-stu-id="0aee1-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="0aee1-103">Forces garbage collection to occur within the common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0aee1-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aee1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0aee1-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0aee1-105">주의</span><span class="sxs-lookup"><span data-stu-id="0aee1-105">Remarks</span></span>  
 <span data-ttu-id="0aee1-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span><span class="sxs-lookup"><span data-stu-id="0aee1-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="0aee1-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span><span class="sxs-lookup"><span data-stu-id="0aee1-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aee1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0aee1-108">Requirements</span></span>  
 <span data-ttu-id="0aee1-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0aee1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aee1-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0aee1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0aee1-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aee1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aee1-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aee1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aee1-113">참조</span><span class="sxs-lookup"><span data-stu-id="0aee1-113">See also</span></span>

- [<span data-ttu-id="0aee1-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0aee1-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
