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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12442eb5596ff3dca49cf24e27040f3e92d3a7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072612"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="92cb3-102">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="92cb3-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="92cb3-103">초기화는 프로세스 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="92cb3-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92cb3-105">구문</span><span class="sxs-lookup"><span data-stu-id="92cb3-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92cb3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92cb3-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="92cb3-107">[in] 이 값을 설정 `true` 만 현재 스레드의;에 대 한 디버깅 지원을 초기화할 수로 설정 `false` 모든 스레드에 대 한 디버깅 지원을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="92cb3-108">[out] 디버깅 세션을 식별 하는 반환 된 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92cb3-109">설명</span><span class="sxs-lookup"><span data-stu-id="92cb3-109">Remarks</span></span>  
 <span data-ttu-id="92cb3-110">CLR 디버깅 서비스.NET Framework 버전 1.0 및 1.1에서에서 제한 된 프로세스에서 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="92cb3-111">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="92cb3-112">그러나 고객 의견 때문에 프로세스의 디버깅 버전 2.0에서에서.NET Framework에서 제거 되어 프로 파일링 API에 따라 더 기능 집합으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="92cb3-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92cb3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92cb3-113">Requirements</span></span>  
 <span data-ttu-id="92cb3-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="92cb3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92cb3-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92cb3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92cb3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92cb3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92cb3-117">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="92cb3-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92cb3-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="92cb3-118">See also</span></span>

- [<span data-ttu-id="92cb3-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92cb3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
