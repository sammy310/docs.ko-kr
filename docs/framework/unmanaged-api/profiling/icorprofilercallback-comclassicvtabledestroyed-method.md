---
title: ICorProfilerCallback::COMClassicVTableDestroyed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63dc9ee81c98a23f01948a142018369eca7210b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598092"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="f1744-102">ICorProfilerCallback::COMClassicVTableDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="f1744-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="f1744-103">COM interop vtable 소멸 되 고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1744-104">이 콜백은 vtable의 소멸 종료 되는 시점과 매우 발생 하기 때문에 발생 하지 않습니다 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1744-105">구문</span><span class="sxs-lookup"><span data-stu-id="f1744-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1744-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1744-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="f1744-107">[in] 이 vtable 생성 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="f1744-108">[in] 클래스에 의해 구현 된 인터페이스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="f1744-109">인터페이스 내부용 으로만 사용 되는 경우이 값은 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="f1744-110">[in] Vtable의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1744-111">설명</span><span class="sxs-lookup"><span data-stu-id="f1744-111">Remarks</span></span>  
 <span data-ttu-id="f1744-112">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 메서드의 구현에서 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f1744-113">프로파일러 여기 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f1744-114">이 메서드 구현은 프로파일러의 관리 되는 메모리 할당에서 또는 관리 코드를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1744-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1744-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1744-115">Requirements</span></span>  
 <span data-ttu-id="f1744-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1744-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1744-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1744-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1744-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1744-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1744-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1744-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1744-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1744-120">See also</span></span>

- [<span data-ttu-id="f1744-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1744-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f1744-122">COMClassicVTableCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="f1744-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
