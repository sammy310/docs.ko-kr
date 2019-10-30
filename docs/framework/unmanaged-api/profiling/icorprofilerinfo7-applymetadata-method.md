---
title: 'ICorProfilerInfo7:: ApplyMetaData 메서드'
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
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130360"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="c441b-102">ICorProfilerInfo7:: ApplyMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="c441b-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="c441b-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="c441b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="c441b-104">`IMetadataEmit::Define*` 메서드에 의해 새로 정의 된 메타 데이터를 지정 된 모듈에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c441b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c441b-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c441b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c441b-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c441b-107">진행 메타 데이터가 변경 된 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c441b-108">주의</span><span class="sxs-lookup"><span data-stu-id="c441b-108">Remarks</span></span>  
 <span data-ttu-id="c441b-109">[Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백을 수행한 후 메타 데이터를 변경 하는 경우 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="c441b-110">`ApplyMetaData`는 다음 형식의 메타 데이터를 추가 하는 것만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="c441b-111">`AssemblyRef` 레코드- [IMetaDataAssemblyEmit::D efineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="c441b-112">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-112">method.</span></span>  
  
- <span data-ttu-id="c441b-113">`TypeRef` 레코드- [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="c441b-114">`TypeSpec` 레코드- [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="c441b-115">`MemberRef` 레코드- [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="c441b-116">`MemberSpec` 레코드- [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="c441b-117">`UserString` 레코드- [IMetaDataEmit::D efineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="c441b-118">.NET Core 3.0부터 `ApplyMetaData`는 다음 유형도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="c441b-119">[IMetaDataEmit::D Efin def](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드를 호출 하 여 만드는 레코드를 `TypeDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="c441b-120">`MethodDef` 레코드- [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) 메서드를 호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="c441b-121">그러나 기존 형식에 가상 메서드를 추가 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="c441b-122">가상 메서드는 [Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 전에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c441b-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="c441b-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c441b-123">Requirements</span></span>  
 <span data-ttu-id="c441b-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c441b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c441b-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c441b-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c441b-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c441b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c441b-127">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c441b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c441b-128">참조</span><span class="sxs-lookup"><span data-stu-id="c441b-128">See also</span></span>

- [<span data-ttu-id="c441b-129">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c441b-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
