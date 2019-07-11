---
title: ICorProfilerCallback::AppDomainCreationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17f7c985b27adbbb2a5c7ddc2bb62fc93a099a45
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763137"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="72759-102">ICorProfilerCallback::AppDomainCreationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="72759-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="72759-103">응용 프로그램 도메인은 생성 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72759-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72759-104">구문</span><span class="sxs-lookup"><span data-stu-id="72759-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72759-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72759-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="72759-106">[in] 생성 되는 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="72759-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72759-107">설명</span><span class="sxs-lookup"><span data-stu-id="72759-107">Remarks</span></span>  
 <span data-ttu-id="72759-108">ID 정보 요청 될 때까지 적합 하지 않습니다.는 [icorprofilercallback:: Appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72759-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72759-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72759-109">Requirements</span></span>  
 <span data-ttu-id="72759-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72759-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72759-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72759-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72759-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72759-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72759-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72759-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72759-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="72759-114">See also</span></span>

- [<span data-ttu-id="72759-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72759-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
