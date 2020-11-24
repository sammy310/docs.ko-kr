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
ms.openlocfilehash: 3f56c3faa10eb05896936a37b0094797b0b6e2b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669174"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="f01a6-102">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="f01a6-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>

<span data-ttu-id="f01a6-103">In-process 디버깅 지원 기능을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="f01a6-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="f01a6-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f01a6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f01a6-106">Parameters</span></span>  

 `fThisThreadOnly`  
 <span data-ttu-id="f01a6-107">진행 `true` 현재 스레드에서만 디버깅 지원을 초기화 하려면이 값을로 설정 하 고, `false` 모든 스레드에 대 한 디버깅 지원을 초기화 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="f01a6-108">제한이 디버깅 세션을 식별 하는 반환 된 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f01a6-109">설명</span><span class="sxs-lookup"><span data-stu-id="f01a6-109">Remarks</span></span>  

 <span data-ttu-id="f01a6-110">CLR 디버깅 서비스는 .NET Framework 버전 1.0 및 1.1에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="f01a6-111">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f01a6-112">그러나 고객의 의견 때문에 2.0 버전의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f01a6-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f01a6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f01a6-113">Requirements</span></span>  

 <span data-ttu-id="f01a6-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f01a6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f01a6-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f01a6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f01a6-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f01a6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f01a6-117">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f01a6-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01a6-118">참조</span><span class="sxs-lookup"><span data-stu-id="f01a6-118">See also</span></span>

- [<span data-ttu-id="f01a6-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f01a6-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
