---
description: '자세히 알아보기: ICorProfilerCallback:: COMClassicVTableCreated 메서드'
title: ICorProfilerCallback::COMClassicVTableCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 134ca44cbcd7a275e3ad61a3dd4decaa92668b5b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657712"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="d8dc0-103">ICorProfilerCallback::COMClassicVTableCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="d8dc0-103">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>

<span data-ttu-id="d8dc0-104">지정 된 IID 및 클래스에 대 한 COM interop vtable이 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-104">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dc0-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8dc0-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8dc0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8dc0-106">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="d8dc0-107">\[in] vtable이 생성 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-107">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="d8dc0-108">\[in] 클래스에서 구현 하는 인터페이스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-108">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="d8dc0-109">인터페이스가 내부 전용 이면이 값은 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-109">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="d8dc0-110">\[in] vtable의 시작에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-110">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="d8dc0-111">\[in] vtable에 있는 슬롯의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-111">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8dc0-112">설명</span><span class="sxs-lookup"><span data-stu-id="d8dc0-112">Remarks</span></span>  

 <span data-ttu-id="d8dc0-113">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-113">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d8dc0-114">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-114">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d8dc0-115">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-115">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8dc0-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8dc0-116">Requirements</span></span>  

 <span data-ttu-id="d8dc0-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8dc0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8dc0-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8dc0-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8dc0-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8dc0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8dc0-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8dc0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dc0-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8dc0-121">See also</span></span>

- [<span data-ttu-id="d8dc0-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8dc0-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d8dc0-123">COMClassicVTableDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="d8dc0-123">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
