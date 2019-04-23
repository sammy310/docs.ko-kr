---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO 구조
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fa1cc05ee583cf1bd59235fcd9821d1c92d21f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101434"
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="6f1de-102">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="6f1de-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="6f1de-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="6f1de-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6f1de-104">어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 어셈블리 참조에 대한 정보를 공용 언어 런타임에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1de-105">구문</span><span class="sxs-lookup"><span data-stu-id="6f1de-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6f1de-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6f1de-106">Members</span></span>  
  
|<span data-ttu-id="6f1de-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6f1de-107">Member</span></span>|<span data-ttu-id="6f1de-108">설명</span><span class="sxs-lookup"><span data-stu-id="6f1de-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="6f1de-109">어셈블리의 공개 키 또는 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="6f1de-110">공개 키 또는 토큰의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="6f1de-111">참조되는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="6f1de-112">어셈블리의 메타데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="6f1de-113">해시 BLOB(Binary Large Object)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="6f1de-114">해시 BLOB의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="6f1de-115">어셈블리의 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f1de-116">설명</span><span class="sxs-lookup"><span data-stu-id="6f1de-116">Remarks</span></span>  
 <span data-ttu-id="6f1de-117">프로파일러는 어셈블리 참조 closure 워커를 수행할 때 공용 언어 런타임이 고려해야 하는 추가 어셈블리 참조를 선언할 때 `COR_PRF_EX_CLAUSE_INFO` 구조체를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="6f1de-118">프로파일러를 등록 하는 경우는 [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드를 런타임에 전달에 대 한 포인터와 함께 로드할 어셈블리의 이름과 경로 [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 인터페이스 개체를 메서드에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="6f1de-119">프로파일러를 호출할 수는 [icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드를 `COR_PRF_ASSEMBLY_REFERENCE_INFO` 에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체는 [ ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f1de-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f1de-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f1de-120">Requirements</span></span>  
 <span data-ttu-id="6f1de-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f1de-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f1de-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f1de-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f1de-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f1de-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f1de-124">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f1de-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1de-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f1de-125">See also</span></span>

- [<span data-ttu-id="6f1de-126">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="6f1de-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="6f1de-127">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="6f1de-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="6f1de-128">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="6f1de-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
