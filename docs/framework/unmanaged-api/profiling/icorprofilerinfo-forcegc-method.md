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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078085"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="c560f-102">ICorProfilerInfo::ForceGC 메서드</span><span class="sxs-lookup"><span data-stu-id="c560f-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="c560f-103">가비지 수집이 CLR (공용 언어 런타임) 내에 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c560f-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c560f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c560f-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c560f-105">설명</span><span class="sxs-lookup"><span data-stu-id="c560f-105">Remarks</span></span>  
 <span data-ttu-id="c560f-106">`ForceGC` 만 스레드에서 관리 코드에 실행 된 적 하 및 스택에 프로파일러 콜백이 없는 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c560f-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="c560f-107">가장 편리 하 게 구현에서 호출 하는 프로파일러는 별도 스레드를 만들 때 `ForceGC` 신호를 받을 때입니다.</span><span class="sxs-lookup"><span data-stu-id="c560f-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c560f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c560f-108">Requirements</span></span>  
 <span data-ttu-id="c560f-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c560f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c560f-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c560f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c560f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c560f-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c560f-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c560f-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c560f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c560f-113">See also</span></span>

- [<span data-ttu-id="c560f-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c560f-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
