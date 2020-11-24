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
ms.openlocfilehash: e929c74ba0f1f33ddbb28476b3c9e0a512567ac6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669057"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="73d62-102">ICorProfilerInfo::EndInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="73d62-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>

<span data-ttu-id="73d62-103">In-process 디버깅 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="73d62-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d62-105">구문</span><span class="sxs-lookup"><span data-stu-id="73d62-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73d62-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73d62-106">Parameters</span></span>  

 `dwProfilerContext`  
 <span data-ttu-id="73d62-107">진행 디버깅 세션을 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="73d62-108">이 값은 [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) 메서드에 수신 된 값과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73d62-109">설명</span><span class="sxs-lookup"><span data-stu-id="73d62-109">Remarks</span></span>  

 <span data-ttu-id="73d62-110">동일한 콜백 메서드 내에서 [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) 를 호출 해야 합니다 `EndInprocDebugging` .</span><span class="sxs-lookup"><span data-stu-id="73d62-110">You must call [ICorProfilerInfo::BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="73d62-111">CLR 디버깅 서비스는 .NET Framework 버전 1.0 및 1.1에서 제한 된 in-process 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="73d62-112">In-process 디버깅은 디버깅 API의 검사 부분을 사용 하는 프로파일러를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="73d62-113">그러나 고객의 의견 때문에 2.0 버전의 .NET Framework에서 in-process 디버깅이 제거 되었고 프로 파일링 API를 사용 하 여 더 많은 기능 집합으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73d62-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d62-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73d62-114">Requirements</span></span>  

 <span data-ttu-id="73d62-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73d62-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73d62-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73d62-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73d62-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73d62-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73d62-118">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="73d62-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d62-119">참조</span><span class="sxs-lookup"><span data-stu-id="73d62-119">See also</span></span>

- [<span data-ttu-id="73d62-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73d62-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
