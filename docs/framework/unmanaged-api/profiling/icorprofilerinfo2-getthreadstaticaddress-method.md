---
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
ms.openlocfilehash: d44eae4da70418e2d4f398b2bacee1fb53d55b60
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443059"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="08fcd-102">ICorProfilerInfo2::GetThreadStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="08fcd-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="08fcd-103">지정 된 스레드의 범위에 있는 지정 된 스레드 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fcd-104">구문</span><span class="sxs-lookup"><span data-stu-id="08fcd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08fcd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08fcd-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="08fcd-106">진행 요청 된 스레드 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="08fcd-107">진행 요청 된 스레드 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="08fcd-108">진행 요청 된 정적 필드의 범위에 해당 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="08fcd-109">제한이 지정 된 스레드 내의 정적 필드 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08fcd-110">설명</span><span class="sxs-lookup"><span data-stu-id="08fcd-110">Remarks</span></span>  
 <span data-ttu-id="08fcd-111">`GetThreadStaticAddress` 메서드는 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="08fcd-112">지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="08fcd-113">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="08fcd-114">이러한 주소는 가비지 수집 후 무효화 될 수 있으므로 가비지 수집 프로파일러가 유효한 것으로 가정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="08fcd-115">클래스의 클래스 생성자가 `GetThreadStaticAddress` 완료 되기 전에는 정적 필드 중 일부는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있는 경우에도 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08fcd-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fcd-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08fcd-116">Requirements</span></span>  
 <span data-ttu-id="08fcd-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08fcd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08fcd-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08fcd-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08fcd-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08fcd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08fcd-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08fcd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fcd-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="08fcd-121">See also</span></span>

- [<span data-ttu-id="08fcd-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08fcd-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="08fcd-123">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08fcd-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
