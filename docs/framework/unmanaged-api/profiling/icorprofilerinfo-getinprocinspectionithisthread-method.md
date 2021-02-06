---
description: '자세히 알아보기: ICorProfilerInfo:: GetInprocInspectionIThisThread 메서드'
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
ms.openlocfilehash: 07ff904170750976e54e623101a2552db0c7f290
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647247"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="c56b0-103">ICorProfilerInfo::GetInprocInspectionIThisThread 메서드</span><span class="sxs-lookup"><span data-stu-id="c56b0-103">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>

<span data-ttu-id="c56b0-104">ICorDebugThread 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c56b0-104">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="c56b0-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c56b0-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56b0-106">구문</span><span class="sxs-lookup"><span data-stu-id="c56b0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c56b0-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c56b0-107">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="c56b0-108">인터페이스에 대해 쿼리할 수 있는 [out](/cpp/atl/iunknown) 개체입니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="c56b0-108">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c56b0-109">설명</span><span class="sxs-lookup"><span data-stu-id="c56b0-109">Remarks</span></span>  

 <span data-ttu-id="c56b0-110">CLR (공용 언어 런타임) 디버깅 서비스는 .NET Framework 버전 1.0에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c56b0-110">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="c56b0-111">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c56b0-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="c56b0-112">고객 피드백의 결과로, 버전 2.0의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c56b0-112">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c56b0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c56b0-113">Requirements</span></span>  

 <span data-ttu-id="c56b0-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c56b0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c56b0-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c56b0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c56b0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c56b0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c56b0-117">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="c56b0-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56b0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c56b0-118">See also</span></span>

- [<span data-ttu-id="c56b0-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c56b0-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
