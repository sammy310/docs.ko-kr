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
ms.openlocfilehash: bcae66fd30c29a0a3c9bd0b5ffc2047efdf3788d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049663"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="668b4-102">ICorProfilerInfo::EndInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="668b4-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="668b4-103">프로세스의 디버깅 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="668b4-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="668b4-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="668b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="668b4-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="668b4-107">[in] 디버깅 세션을 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="668b4-108">이 값에서 수신 하는 것과 동일 해야 합니다 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="668b4-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="668b4-109">설명</span><span class="sxs-lookup"><span data-stu-id="668b4-109">Remarks</span></span>  
 <span data-ttu-id="668b4-110">호출 해야 합니다 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 고 `EndInprocDebugging` 동일한 콜백 메서드 내에서.</span><span class="sxs-lookup"><span data-stu-id="668b4-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="668b4-111">CLR 디버깅 서비스.NET Framework 버전 1.0 및 1.1에서에서 제한 된 프로세스에서 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="668b4-112">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="668b4-113">그러나 고객 의견 때문에 프로세스의 디버깅 버전 2.0에서에서.NET Framework에서 제거 되어 프로 파일링 API에 따라 더 기능 집합으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="668b4-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668b4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="668b4-114">Requirements</span></span>  
 <span data-ttu-id="668b4-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="668b4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668b4-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="668b4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="668b4-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="668b4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="668b4-118">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="668b4-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668b4-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="668b4-119">See also</span></span>

- [<span data-ttu-id="668b4-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="668b4-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
