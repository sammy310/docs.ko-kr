---
title: ICorProfilerInfo::GetInprocInspectionIThisThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 0ab383f0968061667b3580a2058687eecda99dde
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870044"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="e9778-102">ICorProfilerInfo::GetInprocInspectionIThisThread 메서드</span><span class="sxs-lookup"><span data-stu-id="e9778-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="e9778-103">ICorDebugThread 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="e9778-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9778-105">구문</span><span class="sxs-lookup"><span data-stu-id="e9778-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9778-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9778-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="e9778-107">`ICorDebugThread` 인터페이스에 대해 쿼리할 수 있는 [out](/cpp/atl/iunknown) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9778-108">주의</span><span class="sxs-lookup"><span data-stu-id="e9778-108">Remarks</span></span>  
 <span data-ttu-id="e9778-109">CLR (공용 언어 런타임) 디버깅 서비스는 .NET Framework 버전 1.0에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="e9778-110">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="e9778-111">고객 피드백의 결과로, 버전 2.0의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9778-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9778-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9778-112">Requirements</span></span>  
 <span data-ttu-id="e9778-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9778-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9778-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9778-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9778-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9778-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9778-116">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="e9778-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9778-117">참조</span><span class="sxs-lookup"><span data-stu-id="e9778-117">See also</span></span>

- [<span data-ttu-id="e9778-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9778-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
