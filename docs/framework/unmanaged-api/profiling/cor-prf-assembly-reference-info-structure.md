---
description: '다음에 대 한 자세한 정보: COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체'
title: COR_PRF_ASSEMBLY_REFERENCE_INFO 구조
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: fc384e0a302c83af510deefc6f9f3b9cd5a2f77f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649223"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="b3fb2-103">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="b3fb2-103">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>

<span data-ttu-id="b3fb2-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="b3fb2-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b3fb2-105">어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 어셈블리 참조에 대한 정보를 공용 언어 런타임에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-105">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3fb2-106">구문</span><span class="sxs-lookup"><span data-stu-id="b3fb2-106">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b3fb2-107">구성원</span><span class="sxs-lookup"><span data-stu-id="b3fb2-107">Members</span></span>  
  
|<span data-ttu-id="b3fb2-108">멤버</span><span class="sxs-lookup"><span data-stu-id="b3fb2-108">Member</span></span>|<span data-ttu-id="b3fb2-109">설명</span><span class="sxs-lookup"><span data-stu-id="b3fb2-109">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="b3fb2-110">어셈블리의 공개 키 또는 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-110">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="b3fb2-111">공개 키 또는 토큰의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-111">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="b3fb2-112">참조되는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-112">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="b3fb2-113">어셈블리의 메타데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-113">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="b3fb2-114">해시 BLOB(Binary Large Object)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-114">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="b3fb2-115">해시 BLOB의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-115">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="b3fb2-116">어셈블리의 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-116">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3fb2-117">설명</span><span class="sxs-lookup"><span data-stu-id="b3fb2-117">Remarks</span></span>  

 <span data-ttu-id="b3fb2-118">프로파일러는 어셈블리 참조 closure 워커를 수행할 때 공용 언어 런타임이 고려해야 하는 추가 어셈블리 참조를 선언할 때 `COR_PRF_EX_CLAUSE_INFO` 구조체를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-118">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="b3fb2-119">프로파일러가 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드에 등록 하는 경우 런타임은 로드 될 어셈블리의 경로 및 이름과 해당 메서드에 대 한 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스 개체에 대 한 포인터를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-119">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="b3fb2-120">그런 다음 프로파일러는 [](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) `COR_PRF_ASSEMBLY_REFERENCE_INFO` [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백에서 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체를 사용 하 여 ICorProfilerAssemblyReferenceProvider:: addassemblyreference 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-120">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3fb2-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3fb2-121">Requirements</span></span>  

 <span data-ttu-id="b3fb2-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3fb2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3fb2-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3fb2-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3fb2-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3fb2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3fb2-125">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3fb2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fb2-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3fb2-126">See also</span></span>

- [<span data-ttu-id="b3fb2-127">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="b3fb2-127">Profiling Structures</span></span>](profiling-structures.md)
- [<span data-ttu-id="b3fb2-128">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="b3fb2-128">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="b3fb2-129">AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="b3fb2-129">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
