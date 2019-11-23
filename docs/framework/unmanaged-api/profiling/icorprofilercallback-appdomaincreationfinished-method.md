---
title: ICorProfilerCallback::AppDomainCreationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: eaf0ae2a1b86234495c1804cff8b74331b3e8021
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445281"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="4e61f-102">ICorProfilerCallback::AppDomainCreationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="4e61f-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="4e61f-103">Notifies the profiler that an application domain has been created.</span><span class="sxs-lookup"><span data-stu-id="4e61f-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e61f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e61f-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4e61f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e61f-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="4e61f-106">[in] Identifies the domain which has been created.</span><span class="sxs-lookup"><span data-stu-id="4e61f-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4e61f-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span><span class="sxs-lookup"><span data-stu-id="4e61f-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e61f-108">주의</span><span class="sxs-lookup"><span data-stu-id="4e61f-108">Remarks</span></span>  
 <span data-ttu-id="4e61f-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span><span class="sxs-lookup"><span data-stu-id="4e61f-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="4e61f-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="4e61f-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="4e61f-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="4e61f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4e61f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span><span class="sxs-lookup"><span data-stu-id="4e61f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e61f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e61f-113">Requirements</span></span>  
 <span data-ttu-id="4e61f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e61f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e61f-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e61f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e61f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e61f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e61f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e61f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e61f-118">참조</span><span class="sxs-lookup"><span data-stu-id="4e61f-118">See also</span></span>

- [<span data-ttu-id="4e61f-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e61f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
