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
ms.openlocfilehash: 688b9975cc68463de066e5225c6ab1e04cbb5337
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685379"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="1c929-102">ICorProfilerCallback::AppDomainCreationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1c929-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>

<span data-ttu-id="1c929-103">응용 프로그램 도메인이 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c929-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c929-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="1c929-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c929-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="1c929-106">\[in] 생성 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="1c929-107">\[in] 응용 프로그램 도메인 만들기가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c929-108">설명</span><span class="sxs-lookup"><span data-stu-id="1c929-108">Remarks</span></span>  

 <span data-ttu-id="1c929-109">메서드를 호출할 때까지 모든 정보 요청에 대해 응용 프로그램 ID가 유효 하지 않습니다 `AppDomainCreationFinished` .</span><span class="sxs-lookup"><span data-stu-id="1c929-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="1c929-110">응용 프로그램 도메인 로드의 일부 부분은 콜백 후에도 계속 `AppDomainCreationFinished` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="1c929-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1c929-112">그러나의 성공 HRESULT는 `hrStatus` 응용 프로그램 도메인을 만드는 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c929-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c929-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c929-113">Requirements</span></span>  

 <span data-ttu-id="1c929-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c929-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c929-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c929-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c929-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c929-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c929-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c929-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c929-118">참조</span><span class="sxs-lookup"><span data-stu-id="1c929-118">See also</span></span>

- [<span data-ttu-id="1c929-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c929-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
