---
title: IMetaDataEmit::DefineImportMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175865"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="69af1-102">IMetaDataEmit::DefineImportMember 메서드</span><span class="sxs-lookup"><span data-stu-id="69af1-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="69af1-103">현재 범위 외부에 정의된 형식 또는 모듈의 지정된 멤버에 대한 참조를 만들고 해당 참조에 대한 토큰을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69af1-104">구문</span><span class="sxs-lookup"><span data-stu-id="69af1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69af1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69af1-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="69af1-106">【인】 대상 멤버를 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="69af1-107">【인】 `pAssemImport`에서 지정한 어셈블리에 대한 해시가 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="69af1-108">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="69af1-109">【인】 대상 멤버를 가져오는 메타데이터 범위를 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="69af1-110">【인】 대상 멤버를 지정하는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="69af1-111">토큰은 `mdMethodDef` (멤버 메서드에 대한), `mdProperty` (멤버 속성에 `mdFieldDef` 대한) 또는 (멤버 필드의) 토큰일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="69af1-112">【인】 대상 멤버를 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="69af1-113">【인】 대상 `mdTypeRef` `mdModuleRef` 멤버를 소유하는 형식 또는 모듈에 대한 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="69af1-114">【아웃】 멤버 `mdMemberRef` 참조의 현재 범위에 정의된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69af1-115">설명</span><span class="sxs-lookup"><span data-stu-id="69af1-115">Remarks</span></span>  
 <span data-ttu-id="69af1-116">메서드는 `DefineImportMember` 다른 범위에 정의 `mbMember`된 에 의해 지정 된 `pImport`멤버를 검색 하 고 해당 속성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="69af1-117">이 정보를 사용하여 현재 범위의 [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드를 호출하여 멤버 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="69af1-118">일반적으로 메서드를 `DefineImportMember` 사용하기 전에 현재 범위에서 대상 멤버의 상위 클래스, 인터페이스 또는 모듈에 대한 형식 참조 또는 모듈 참조를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="69af1-119">그런 다음 이 참조에 대한 `tkParent` 메타데이터 토큰이 인수에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="69af1-120">나중에 컴파일러 또는 링커에 의해 해결될 경우 대상 멤버의 부모에 대한 참조를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="69af1-121">요약하면</span><span class="sxs-lookup"><span data-stu-id="69af1-121">To summarize:</span></span>  
  
- <span data-ttu-id="69af1-122">대상 멤버가 필드 또는 메서드인 경우 [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 또는 [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) 메서드를 사용하여 현재 범위에서 멤버의 상위 클래스 또는 상위 인터페이스에 대한 형식 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="69af1-123">대상 멤버가 전역 변수 또는 전역 함수인 경우(즉, 클래스 또는 인터페이스의 구성원이 아님) [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) 메서드를 사용하여 멤버의 상위 모듈에 대한 현재 범위에서 모듈 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="69af1-124">대상 멤버의 부모가 나중에 컴파일러 또는 링커에 의해 해결되면 `mdTokenNil` `tkParent`에서 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="69af1-125">이것이 적용되는 유일한 시나리오는 전역 함수 또는 전역 변수를 현재 모듈에 연결되고 메타데이터가 병합되는 .obj 파일에서 가져오는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="69af1-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69af1-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69af1-126">Requirements</span></span>  
 <span data-ttu-id="69af1-127">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69af1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69af1-128">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="69af1-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69af1-129">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="69af1-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69af1-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69af1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69af1-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69af1-131">See also</span></span>

- [<span data-ttu-id="69af1-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69af1-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="69af1-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69af1-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
