---
description: '자세히 알아보기: ICorProfilerInfo2:: GetThreadStaticAddress 메서드'
title: ICorProfilerInfo2::GetThreadStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
ms.openlocfilehash: bab4190f3751967031806dccbea2fdf6add73f6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647054"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="688fb-103">ICorProfilerInfo2::GetThreadStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="688fb-103">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>

<span data-ttu-id="688fb-104">지정 된 스레드의 범위에 있는 지정 된 스레드 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-104">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="688fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="688fb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="688fb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="688fb-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="688fb-107">진행 요청 된 스레드 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-107">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="688fb-108">진행 요청 된 스레드 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-108">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="688fb-109">진행 요청 된 정적 필드의 범위에 해당 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="688fb-110">제한이 지정 된 스레드 내의 정적 필드 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="688fb-111">설명</span><span class="sxs-lookup"><span data-stu-id="688fb-111">Remarks</span></span>  

 <span data-ttu-id="688fb-112">`GetThreadStaticAddress`메서드는 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-112">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="688fb-113">지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="688fb-114">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="688fb-115">이러한 주소는 가비지 수집 후 무효화 될 수 있으므로 가비지 수집 프로파일러가 유효한 것으로 가정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-115">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="688fb-116">클래스의 클래스 생성자가 완료 되기 전에는 `GetThreadStaticAddress` 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 하지만, 일부 정적 필드는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="688fb-116">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="688fb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="688fb-117">Requirements</span></span>  

 <span data-ttu-id="688fb-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="688fb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="688fb-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="688fb-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="688fb-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="688fb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="688fb-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="688fb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688fb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="688fb-122">See also</span></span>

- [<span data-ttu-id="688fb-123">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="688fb-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="688fb-124">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="688fb-124">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
