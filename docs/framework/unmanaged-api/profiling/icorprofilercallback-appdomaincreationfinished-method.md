---
description: '자세히 알아보기: ICorProfilerCallback:: AppDomainCreationFinished 메서드'
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
ms.openlocfilehash: 51ed9ba19d96fd6ea05d05b07fe329aa9c01f290
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760758"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="1e0ec-103">ICorProfilerCallback::AppDomainCreationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1e0ec-103">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>

<span data-ttu-id="1e0ec-104">응용 프로그램 도메인이 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-104">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e0ec-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="1e0ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e0ec-106">Parameters</span></span>

<span data-ttu-id="1e0ec-107">`appDomainId` 진행 만든 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-107">`appDomainId` [in] Identifies the domain which has been created.</span></span>

<span data-ttu-id="1e0ec-108">`hrStatus` 진행 응용 프로그램 도메인 만들기가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-108">`hrStatus` [in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e0ec-109">설명</span><span class="sxs-lookup"><span data-stu-id="1e0ec-109">Remarks</span></span>  

 <span data-ttu-id="1e0ec-110">메서드를 호출할 때까지 모든 정보 요청에 대해 응용 프로그램 ID가 유효 하지 않습니다 `AppDomainCreationFinished` .</span><span class="sxs-lookup"><span data-stu-id="1e0ec-110">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="1e0ec-111">응용 프로그램 도메인 로드의 일부 부분은 콜백 후에도 계속 `AppDomainCreationFinished` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-111">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="1e0ec-112">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1e0ec-113">그러나의 성공 HRESULT는 `hrStatus` 응용 프로그램 도메인을 만드는 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-113">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e0ec-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e0ec-114">Requirements</span></span>  

 <span data-ttu-id="1e0ec-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e0ec-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e0ec-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e0ec-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e0ec-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e0ec-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e0ec-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e0ec-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0ec-119">참조</span><span class="sxs-lookup"><span data-stu-id="1e0ec-119">See also</span></span>

- [<span data-ttu-id="1e0ec-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e0ec-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
