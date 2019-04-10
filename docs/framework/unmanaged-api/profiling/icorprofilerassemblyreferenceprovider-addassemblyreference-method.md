---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09ce4f3a293e7870ddadf4ad6ee2c15de10f4594
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200573"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="1eb34-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="1eb34-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="1eb34-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="1eb34-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1eb34-104">프로파일러가에 추가 하는 어셈블리 참조를 CLR (공용 언어 런타임)를 알려주는 합니다 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb34-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb34-105">구문</span><span class="sxs-lookup"><span data-stu-id="1eb34-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb34-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1eb34-106">Parameters</span></span>  
 <span data-ttu-id="1eb34-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="1eb34-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="1eb34-108">에 대 한 포인터를 [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) CLR 어셈블리 참조 closure 워커를 수행할 때 고려해 야 하는 어셈블리 참조에 대 한 정보를 사용 하 여 제공 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1eb34-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eb34-109">설명</span><span class="sxs-lookup"><span data-stu-id="1eb34-109">Remarks</span></span>  
 <span data-ttu-id="1eb34-110">에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대해이 메서드를 호출 하는 프로파일러를 `wszAssemblyPath` 인수를 [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb34-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="1eb34-111">합니다 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 프로파일러의 인터페이스 개체가 전달 됩니다 [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 어셈블리 경로 및 이름과 함께 콜백 합니다 `wszAssemblyPath` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="1eb34-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb34-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eb34-112">Requirements</span></span>  
 <span data-ttu-id="1eb34-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1eb34-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb34-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1eb34-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1eb34-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eb34-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1eb34-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1eb34-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1eb34-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="1eb34-117">See also</span></span>

- [<span data-ttu-id="1eb34-118">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eb34-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="1eb34-119">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="1eb34-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="1eb34-120">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1eb34-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
