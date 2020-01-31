---
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
ms.openlocfilehash: 13a298451c3e8e1c5809cc1cb222acb5ab85714b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866691"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="40814-102">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40814-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="40814-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="40814-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="40814-104">프로파일러가 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 콜백에서 추가 될 어셈블리 참조의 CLR (공용 언어 런타임)에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40814-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40814-105">메서드</span><span class="sxs-lookup"><span data-stu-id="40814-105">Methods</span></span>  
  
|<span data-ttu-id="40814-106">메서드</span><span class="sxs-lookup"><span data-stu-id="40814-106">Method</span></span>|<span data-ttu-id="40814-107">설명</span><span class="sxs-lookup"><span data-stu-id="40814-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40814-108">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="40814-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="40814-109">프로파일러가 [Moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백에서 추가 하려고 하는 어셈블리 참조의 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="40814-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40814-110">주의</span><span class="sxs-lookup"><span data-stu-id="40814-110">Remarks</span></span>  
 <span data-ttu-id="40814-111">CLR은 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백의 `ICorProfilerAssemblyReferenceProvider` 인터페이스 개체를 프로파일러에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="40814-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="40814-112">이를 통해 프로파일러에서 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)에서 나중에 추가 하려는 어셈블리 참조의 CLR에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40814-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="40814-113">있습니다.</span><span class="sxs-lookup"><span data-stu-id="40814-113">callback.</span></span> <span data-ttu-id="40814-114">그러면 CLR 어셈블리 참조 closure 워커의 정확도 및 어셈블리 공유 가능 여부를 확인하는 알고리즘의 정확도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="40814-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="40814-115">이 인터페이스는이 인터페이스 개체를 프로파일러에 전달 하는 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40814-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40814-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40814-116">Requirements</span></span>  
 <span data-ttu-id="40814-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40814-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40814-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40814-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40814-119">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40814-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40814-120">참조</span><span class="sxs-lookup"><span data-stu-id="40814-120">See also</span></span>

- [<span data-ttu-id="40814-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40814-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
