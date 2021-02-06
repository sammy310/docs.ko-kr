---
description: '자세히 알아보기: ICorProfilerCallback:: AppDomainShutdownStarted 메서드'
title: ICorProfilerCallback::AppDomainShutdownStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: 16545142a512ca1c5f4167f61b81ea949e3d14e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648118"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="7766e-103">ICorProfilerCallback::AppDomainShutdownStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="7766e-103">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="7766e-104">응용 프로그램 도메인이 프로세스에서 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7766e-104">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7766e-105">구문</span><span class="sxs-lookup"><span data-stu-id="7766e-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7766e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7766e-106">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="7766e-107">\[in] 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7766e-107">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="7766e-108">설명</span><span class="sxs-lookup"><span data-stu-id="7766e-108">Remarks</span></span>  

 <span data-ttu-id="7766e-109">메서드가 반환 된 후에는 값이 `appDomainId` 유효 하지 않습니다 `AppDomainShutdownStarted` . 즉,이 응용 프로그램 도메인에 대 한 정보를 가져올 수 있는 프로파일러의 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="7766e-109">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7766e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7766e-110">Requirements</span></span>  

 <span data-ttu-id="7766e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7766e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7766e-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7766e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7766e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7766e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7766e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7766e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7766e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7766e-115">See also</span></span>

- [<span data-ttu-id="7766e-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7766e-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
