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
ms.openlocfilehash: 04ba37b9c1307539c9fdf299f4667e7026d571be
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760576"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="3261e-103">ICorProfilerCallback::COMClassicVTableCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="3261e-103">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>

<span data-ttu-id="3261e-104">지정 된 IID 및 클래스에 대 한 COM interop vtable이 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-104">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3261e-105">구문</span><span class="sxs-lookup"><span data-stu-id="3261e-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3261e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3261e-106">Parameters</span></span>

<span data-ttu-id="3261e-107">`wrappedClasId` 진행 Vtable이 생성 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-107">`wrappedClasId` [in] The ID of the class for which the vtable has been created.</span></span>

<span data-ttu-id="3261e-108">`implementedIID` 진행 클래스에서 구현 하는 인터페이스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-108">`implementedIID` [in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="3261e-109">인터페이스가 내부 전용 이면이 값은 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-109">This value may be NULL if the interface is internal only.</span></span>

<span data-ttu-id="3261e-110">`pVTable` 진행 Vtable의 시작에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-110">`pVTable` [in] A pointer to the start of the vtable.</span></span>

<span data-ttu-id="3261e-111">`cSlots` 진행 Vtable에 있는 슬롯의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-111">`cSlots` [in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="3261e-112">설명</span><span class="sxs-lookup"><span data-stu-id="3261e-112">Remarks</span></span>  

 <span data-ttu-id="3261e-113">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-113">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="3261e-114">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-114">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="3261e-115">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3261e-115">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3261e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3261e-116">Requirements</span></span>  

 <span data-ttu-id="3261e-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3261e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3261e-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3261e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3261e-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3261e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3261e-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3261e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3261e-121">참조</span><span class="sxs-lookup"><span data-stu-id="3261e-121">See also</span></span>

- [<span data-ttu-id="3261e-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3261e-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3261e-123">COMClassicVTableDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="3261e-123">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
