---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9d1cf182eaf6f245baa5d898bac3ca7d3190234
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763098"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="55425-102">ICorProfilerCallback::AppDomainShutdownStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="55425-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="55425-103">프로세스에서 응용 프로그램 도메인이 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="55425-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55425-104">구문</span><span class="sxs-lookup"><span data-stu-id="55425-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55425-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55425-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="55425-106">[in] 응용 프로그램의 어셈블리 저장 되는 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="55425-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55425-107">설명</span><span class="sxs-lookup"><span data-stu-id="55425-107">Remarks</span></span>  
 <span data-ttu-id="55425-108">변수의 `appDomainId` 후 정보 요청에 적합 하지 않습니다는 `AppDomainShutdownStarted` 메서드가 반환 되는-프로파일러의이 응용 프로그램 도메인에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="55425-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55425-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55425-109">Requirements</span></span>  
 <span data-ttu-id="55425-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55425-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55425-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55425-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55425-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55425-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55425-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55425-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55425-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="55425-114">See also</span></span>

- [<span data-ttu-id="55425-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55425-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
