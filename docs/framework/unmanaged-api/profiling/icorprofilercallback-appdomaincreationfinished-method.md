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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35dac5fd000f5ae30af917e3813239b2e365e64a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598561"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="30f0b-102">ICorProfilerCallback::AppDomainCreationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="30f0b-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="30f0b-103">응용 프로그램 도메인이 만들어졌는지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="30f0b-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="30f0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30f0b-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="30f0b-106">[in] 작성 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="30f0b-107">[in] 응용 프로그램 도메인을 만드는 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30f0b-108">설명</span><span class="sxs-lookup"><span data-stu-id="30f0b-108">Remarks</span></span>  
 <span data-ttu-id="30f0b-109">응용 프로그램 ID까지 정보 요청에 대해 올바르지 않습니다.는 `AppDomainCreationFinished` 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="30f0b-110">일부 응용 프로그램 도메인을 로드 한 후 계속 사용할 수는 `AppDomainCreationFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="30f0b-111">오류 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="30f0b-112">그러나 성공 HRESULT에서 `hrStatus` 응용 프로그램 도메인을 만드는 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30f0b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f0b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30f0b-113">Requirements</span></span>  
 <span data-ttu-id="30f0b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30f0b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f0b-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30f0b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30f0b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30f0b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30f0b-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f0b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f0b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="30f0b-118">See also</span></span>

- [<span data-ttu-id="30f0b-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30f0b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
