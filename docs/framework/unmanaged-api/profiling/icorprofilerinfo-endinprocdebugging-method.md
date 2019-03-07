---
title: ICorProfilerInfo::EndInprocDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f86c680a10a3dcb1009b4f0cedd777ab9da5ac1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501749"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="0bec0-102">ICorProfilerInfo::EndInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="0bec0-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="0bec0-103">프로세스의 디버깅 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="0bec0-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bec0-105">구문</span><span class="sxs-lookup"><span data-stu-id="0bec0-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bec0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bec0-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="0bec0-107">[in] 디버깅 세션을 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="0bec0-108">이 값에서 수신 하는 것과 동일 해야 합니다 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0bec0-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bec0-109">설명</span><span class="sxs-lookup"><span data-stu-id="0bec0-109">Remarks</span></span>  
 <span data-ttu-id="0bec0-110">호출 해야 합니다 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 고 `EndInprocDebugging` 동일한 콜백 메서드 내에서.</span><span class="sxs-lookup"><span data-stu-id="0bec0-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="0bec0-111">CLR 디버깅 서비스.NET Framework 버전 1.0 및 1.1에서에서 제한 된 프로세스에서 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="0bec0-112">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="0bec0-113">그러나 고객 의견 때문에 프로세스의 디버깅 버전 2.0에서에서.NET Framework에서 제거 되어 프로 파일링 API에 따라 더 기능 집합으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bec0-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bec0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bec0-114">Requirements</span></span>  
 <span data-ttu-id="0bec0-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bec0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bec0-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bec0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0bec0-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bec0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bec0-118">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="0bec0-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bec0-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bec0-119">See also</span></span>
- [<span data-ttu-id="0bec0-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bec0-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
