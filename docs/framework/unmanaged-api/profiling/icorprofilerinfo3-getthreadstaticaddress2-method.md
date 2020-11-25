---
title: ICorProfilerInfo3::GetThreadStaticAddress2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: d8f2788d63f27aac30cf239b410eecea31f09212
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697885"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="b9a9c-102">ICorProfilerInfo3::GetThreadStaticAddress2 메서드</span><span class="sxs-lookup"><span data-stu-id="b9a9c-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>

<span data-ttu-id="b9a9c-103">지정된 스레드 및 애플리케이션 도메인의 범위에 있는 지정된 Thread 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9a9c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9a9c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9a9c-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="b9a9c-106">진행 요청 된 스레드 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b9a9c-107">진행 요청 된 스레드 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="b9a9c-108">[in] 애플리케이션 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="b9a9c-109">진행 요청 된 정적 필드의 범위에 해당 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b9a9c-110">제한이 지정 된 스레드 내의 정적 필드 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9a9c-111">설명</span><span class="sxs-lookup"><span data-stu-id="b9a9c-111">Remarks</span></span>  

 <span data-ttu-id="b9a9c-112">`GetThreadStaticAddress2`메서드는 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="b9a9c-113">지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="b9a9c-114">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b9a9c-115">이러한 주소는 가비지 수집 후에 무효화 될 수 있으므로 가비지 수집 후 프로파일러는 이러한 주소를 유효한 것으로 가정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b9a9c-116">클래스의 클래스 생성자가 완료 되기 전에는 `GetThreadStaticAddress2` 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 하지만, 일부 정적 필드는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="b9a9c-117">[ICorProfilerInfo2:: GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) 메서드는 `GetThreadStaticAddress2` 메서드와 유사 하지만 응용 프로그램 도메인 인수를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-117">The [ICorProfilerInfo2::GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a9c-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9a9c-118">Requirements</span></span>  

 <span data-ttu-id="b9a9c-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a9c-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9a9c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9a9c-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9a9c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9a9c-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a9c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a9c-123">참조</span><span class="sxs-lookup"><span data-stu-id="b9a9c-123">See also</span></span>

- [<span data-ttu-id="b9a9c-124">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9a9c-124">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b9a9c-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9a9c-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b9a9c-126">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b9a9c-126">Profiling</span></span>](index.md)
