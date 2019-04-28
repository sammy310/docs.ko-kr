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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598663"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="25ebd-102">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ebd-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="25ebd-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="25ebd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="25ebd-104">CLR (공용 언어 런타임)에 추가할 어셈블리 참조를 알리기 위해 프로파일러를 사용 하도록 설정 합니다 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25ebd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="25ebd-105">Methods</span></span>  
  
|<span data-ttu-id="25ebd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="25ebd-106">Method</span></span>|<span data-ttu-id="25ebd-107">설명</span><span class="sxs-lookup"><span data-stu-id="25ebd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25ebd-108">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="25ebd-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="25ebd-109">CLR 프로파일러가에 추가 하는 어셈블리 참조에 알립니다 합니다 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25ebd-110">설명</span><span class="sxs-lookup"><span data-stu-id="25ebd-110">Remarks</span></span>  
 <span data-ttu-id="25ebd-111">CLR 프로파일러에 전달 된 `ICorProfilerAssemblyReferenceProvider` 인터페이스 개체를 [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백.</span><span class="sxs-lookup"><span data-stu-id="25ebd-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="25ebd-112">이렇게 하면 CLR 프로파일러가 나중에 추가 하는 어셈블리 참조에 알리기 위해 프로파일러를 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="25ebd-113">있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-113">callback.</span></span> <span data-ttu-id="25ebd-114">그러면 CLR 어셈블리 참조 closure 워커의 정확도 및 어셈블리 공유 가능 여부를 확인하는 알고리즘의 정확도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="25ebd-115">이 인터페이스에만 사용할 수 있습니다 합니다 [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 프로파일러에이 인터페이스 개체를 전달 하는 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ebd-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ebd-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25ebd-116">Requirements</span></span>  
 <span data-ttu-id="25ebd-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="25ebd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ebd-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25ebd-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25ebd-119">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ebd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ebd-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="25ebd-120">See also</span></span>

- [<span data-ttu-id="25ebd-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ebd-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
