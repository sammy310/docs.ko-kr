---
title: ICorProfilerInfo7::ApplyMetaData 메서드
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7fa8e2f06faa399734c44b1a52b41246296ef3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498915"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="251bd-102">ICorProfilerInfo7::ApplyMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="251bd-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="251bd-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="251bd-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="251bd-104">새로 정의한 메타 데이터를 적용 합니다 `IMetadataEmit::Define*` 지정된 된 모듈에는 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="251bd-105">구문</span><span class="sxs-lookup"><span data-stu-id="251bd-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="251bd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="251bd-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="251bd-107">[in] 해당 메타 데이터가 변경 된 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="251bd-108">설명</span><span class="sxs-lookup"><span data-stu-id="251bd-108">Remarks</span></span>  
 <span data-ttu-id="251bd-109">후 메타 데이터를 변경 하는 경우는 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="251bd-110">`ApplyMetaData` 다음과 같은 유형의 메타 데이터를 추가 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="251bd-111">`AssemblyRef` 호출 하 여 만든 레코드를 [imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="251bd-112">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-112">method.</span></span>  
  
-   <span data-ttu-id="251bd-113">`TypeRef` 호출 하 여 만든 레코드를 [imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="251bd-114">`TypeSpec` 호출 하 여 만든 레코드를 [imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="251bd-115">`MemberRef` 호출 하 여 만든 레코드를 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="251bd-116">`MemberSpec` 호출 하 여 만든 레코드를 [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="251bd-117">`UserString` 호출 하 여 만든 레코드를 [imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="251bd-118">.NET Core 3.0부터 `ApplyMetaData` 도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="251bd-119">`TypeDef` 호출 하 여 만든 레코드를 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="251bd-120">`MethodDef` 호출 하 여 만든 레코드를 [imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="251bd-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="251bd-121">그러나 가상 메서드를 기존 형식에 추가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="251bd-122">하기 전에 가상 메서드를 추가 해야 합니다 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="251bd-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="251bd-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="251bd-123">Requirements</span></span>  
 <span data-ttu-id="251bd-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="251bd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="251bd-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="251bd-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="251bd-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="251bd-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="251bd-127">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="251bd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="251bd-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="251bd-128">See also</span></span>
- [<span data-ttu-id="251bd-129">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="251bd-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
