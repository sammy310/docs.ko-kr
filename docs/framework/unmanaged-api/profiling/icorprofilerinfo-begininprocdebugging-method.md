---
description: '자세히 알아보기: ICorProfilerInfo:: BeginInprocDebugging 메서드'
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
ms.openlocfilehash: 151aa3604d61e4c5d9e7e24fe9f17bf754d72233
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737404"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="edacd-103">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="edacd-103">ICorProfilerInfo::BeginInprocDebugging Method</span></span>

<span data-ttu-id="edacd-104">In-process 디버깅 지원 기능을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-104">Initializes in-process debugging support.</span></span> <span data-ttu-id="edacd-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edacd-106">구문</span><span class="sxs-lookup"><span data-stu-id="edacd-106">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edacd-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="edacd-107">Parameters</span></span>  

 `fThisThreadOnly`  
 <span data-ttu-id="edacd-108">진행 `true` 현재 스레드에서만 디버깅 지원을 초기화 하려면이 값을로 설정 하 고, `false` 모든 스레드에 대 한 디버깅 지원을 초기화 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-108">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="edacd-109">제한이 디버깅 세션을 식별 하는 반환 된 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-109">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edacd-110">설명</span><span class="sxs-lookup"><span data-stu-id="edacd-110">Remarks</span></span>  

 <span data-ttu-id="edacd-111">CLR 디버깅 서비스는 .NET Framework 버전 1.0 및 1.1에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="edacd-112">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="edacd-113">그러나 고객의 의견 때문에 2.0 버전의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="edacd-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edacd-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="edacd-114">Requirements</span></span>  

 <span data-ttu-id="edacd-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="edacd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edacd-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edacd-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edacd-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edacd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edacd-118">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="edacd-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edacd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edacd-119">See also</span></span>

- [<span data-ttu-id="edacd-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="edacd-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
