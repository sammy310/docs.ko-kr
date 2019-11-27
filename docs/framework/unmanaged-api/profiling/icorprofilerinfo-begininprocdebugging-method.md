---
title: ICorProfilerInfo::BeginInprocDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447743"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="49fd3-102">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="49fd3-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="49fd3-103">In-process 디버깅 지원 기능을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="49fd3-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fd3-105">구문</span><span class="sxs-lookup"><span data-stu-id="49fd3-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49fd3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49fd3-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="49fd3-107">진행 현재 스레드에서만 디버깅 지원을 초기화 하려면이 값을 `true` 설정 합니다. 모든 스레드에 대 한 디버깅 지원을 초기화 하려면 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="49fd3-108">제한이 디버깅 세션을 식별 하는 반환 된 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49fd3-109">주의</span><span class="sxs-lookup"><span data-stu-id="49fd3-109">Remarks</span></span>  
 <span data-ttu-id="49fd3-110">CLR 디버깅 서비스는 .NET Framework 버전 1.0 및 1.1에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="49fd3-111">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="49fd3-112">그러나 고객의 의견 때문에 2.0 버전의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49fd3-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49fd3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49fd3-113">Requirements</span></span>  
 <span data-ttu-id="49fd3-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49fd3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fd3-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49fd3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49fd3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49fd3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49fd3-117">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="49fd3-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fd3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49fd3-118">See also</span></span>

- [<span data-ttu-id="49fd3-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49fd3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
