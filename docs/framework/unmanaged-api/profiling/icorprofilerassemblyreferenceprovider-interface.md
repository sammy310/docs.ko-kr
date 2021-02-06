---
description: '자세히 알아보기: ICorProfilerAssemblyReferenceProvider 인터페이스'
title: ICorProfilerAssemblyReferenceProvider 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 0f16bad95dba46452ce5cc8ad1bbe6ca1bfeb7c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648352"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="7e442-103">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e442-103">ICorProfilerAssemblyReferenceProvider Interface</span></span>

<span data-ttu-id="7e442-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="7e442-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7e442-105">프로파일러가 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 콜백에서 추가 될 어셈블리 참조의 CLR (공용 언어 런타임)에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-105">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e442-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7e442-106">Methods</span></span>  
  
|<span data-ttu-id="7e442-107">메서드</span><span class="sxs-lookup"><span data-stu-id="7e442-107">Method</span></span>|<span data-ttu-id="7e442-108">설명</span><span class="sxs-lookup"><span data-stu-id="7e442-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e442-109">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="7e442-109">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="7e442-110">프로파일러가 [Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백에서 추가 하려고 하는 어셈블리 참조의 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-110">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e442-111">설명</span><span class="sxs-lookup"><span data-stu-id="7e442-111">Remarks</span></span>  

 <span data-ttu-id="7e442-112">CLR은 `ICorProfilerAssemblyReferenceProvider` [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백에서 인터페이스 개체를 프로파일러에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-112">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="7e442-113">이를 통해 프로파일러에서 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)에서 나중에 추가 하려는 어셈블리 참조의 CLR에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-113">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="7e442-114">있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-114">callback.</span></span> <span data-ttu-id="7e442-115">그러면 CLR 어셈블리 참조 closure 워커의 정확도 및 어셈블리 공유 가능 여부를 확인하는 알고리즘의 정확도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-115">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="7e442-116">이 인터페이스는이 인터페이스 개체를 프로파일러에 전달 하는 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e442-116">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e442-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e442-117">Requirements</span></span>  

 <span data-ttu-id="7e442-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e442-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e442-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e442-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e442-120">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e442-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e442-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e442-121">See also</span></span>

- [<span data-ttu-id="7e442-122">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e442-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
