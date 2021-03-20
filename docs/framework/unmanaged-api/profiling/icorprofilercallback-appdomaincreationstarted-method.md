---
description: '자세히 알아보기: ICorProfilerCallback:: AppDomainCreationStarted 메서드'
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
ms.openlocfilehash: b783bb652bed3b600c1e4524810620bab68f5f7a
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760706"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="5eb0a-103">ICorProfilerCallback::AppDomainCreationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5eb0a-103">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>

<span data-ttu-id="5eb0a-104">응용 프로그램 도메인이 생성 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5eb0a-104">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb0a-105">구문</span><span class="sxs-lookup"><span data-stu-id="5eb0a-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eb0a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5eb0a-106">Parameters</span></span>

<span data-ttu-id="5eb0a-107">`appDomainId` 진행 만들고 있는 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb0a-107">`appDomainId` [in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5eb0a-108">설명</span><span class="sxs-lookup"><span data-stu-id="5eb0a-108">Remarks</span></span>  

 <span data-ttu-id="5eb0a-109">[ICorProfilerCallback:: AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대해 ID가 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb0a-109">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eb0a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5eb0a-110">Requirements</span></span>  

 <span data-ttu-id="5eb0a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eb0a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb0a-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5eb0a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5eb0a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5eb0a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eb0a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb0a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb0a-115">참조</span><span class="sxs-lookup"><span data-stu-id="5eb0a-115">See also</span></span>

- [<span data-ttu-id="5eb0a-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eb0a-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
