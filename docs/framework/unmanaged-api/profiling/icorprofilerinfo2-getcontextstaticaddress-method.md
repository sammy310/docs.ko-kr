---
description: '자세히 알아보기: ICorProfilerInfo2:: GetContextStaticAddress 메서드'
title: ICorProfilerInfo2::GetContextStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: 7ea8b81c8b1dba4577e070eda68e760cc39f9131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760506"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="c5c8f-103">ICorProfilerInfo2::GetContextStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="c5c8f-103">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>

<span data-ttu-id="c5c8f-104">지정 된 컨텍스트 범위에 있는 지정 된 컨텍스트 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-104">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c8f-105">구문</span><span class="sxs-lookup"><span data-stu-id="c5c8f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5c8f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5c8f-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="c5c8f-107">진행 요청 된 컨텍스트 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-107">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="c5c8f-108">진행 요청 된 컨텍스트 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-108">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="c5c8f-109">진행 요청 된 컨텍스트 정적 필드에 대 한 범위인 컨텍스트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-109">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="c5c8f-110">제한이 지정 된 컨텍스트 내에 있는 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-110">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5c8f-111">설명</span><span class="sxs-lookup"><span data-stu-id="c5c8f-111">Remarks</span></span>  

 <span data-ttu-id="c5c8f-112">`GetContextStaticAddress`메서드는 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-112">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="c5c8f-113">지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="c5c8f-114">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="c5c8f-115">이러한 주소는 가비지 수집 후에 무효화 될 수 있으므로 가비지 수집 후 프로파일러는 이러한 주소를 유효한 것으로 가정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="c5c8f-116">클래스의 클래스 생성자가 완료 되기 전에는 `GetContextStaticAddress` 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 하지만, 일부 정적 필드는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-116">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5c8f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5c8f-117">Requirements</span></span>  

 <span data-ttu-id="c5c8f-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5c8f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5c8f-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5c8f-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5c8f-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5c8f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5c8f-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5c8f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c8f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5c8f-122">See also</span></span>

- [<span data-ttu-id="c5c8f-123">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5c8f-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c5c8f-124">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5c8f-124">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
