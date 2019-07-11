---
title: ICorProfilerInfo::GetInprocInspectionInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67a680727e824cbe29b9e022e00d661e8694f153
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780561"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="3b39d-102">ICorProfilerInfo::GetInprocInspectionInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="3b39d-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="3b39d-103">"ICorDebugProcess" 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="3b39d-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b39d-105">구문</span><span class="sxs-lookup"><span data-stu-id="3b39d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b39d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b39d-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="3b39d-107">[out](/cpp/atl/iunknown) 에 대해 쿼리할 수 있는 개체는 `ICorDebugProcess` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b39d-108">설명</span><span class="sxs-lookup"><span data-stu-id="3b39d-108">Remarks</span></span>  
 <span data-ttu-id="3b39d-109">디버깅 API 공용 언어 런타임 (CLR).NET Framework 버전 1.0에서에서 제한 된 프로세스에서 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="3b39d-110">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="3b39d-111">고객 피드백의 결과로 in process 디버깅 버전 2.0에서에서.NET Framework에서 제거 되어 프로 파일링 API에 따라 더 기능 집합으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b39d-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b39d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b39d-112">Requirements</span></span>  
 <span data-ttu-id="3b39d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b39d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b39d-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b39d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b39d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b39d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b39d-116">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="3b39d-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b39d-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b39d-117">See also</span></span>

- [<span data-ttu-id="3b39d-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b39d-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
