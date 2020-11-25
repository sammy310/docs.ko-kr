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
ms.openlocfilehash: 60210bc8f93294c3c3380c36096f3e80e5b26643
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723261"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="b4c69-102">IMetaDataEmit::DefineImportMember 메서드</span><span class="sxs-lookup"><span data-stu-id="b4c69-102">IMetaDataEmit::DefineImportMember Method</span></span>

<span data-ttu-id="b4c69-103">현재 범위 외부에 정의 된 형식 또는 모듈의 지정 된 멤버에 대 한 참조를 만들고 해당 참조에 대 한 토큰을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c69-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4c69-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4c69-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4c69-105">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="b4c69-106">진행 대상 멤버를 가져올 어셈블리를 나타내는 [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="b4c69-107">진행 에 지정 된 어셈블리에 대 한 해시를 포함 하는 배열입니다 `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="b4c69-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="b4c69-108">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="b4c69-109">진행 대상 멤버를 가져올 메타 데이터 범위를 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="b4c69-110">진행 대상 멤버를 지정 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="b4c69-111">토큰은 `mdMethodDef` (멤버 메서드의 경우), `mdProperty` (멤버 속성의 경우) 또는 `mdFieldDef` (멤버 필드의 경우) 토큰 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="b4c69-112">진행 대상 멤버를 가져올 대상 어셈블리를 나타내는 [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="b4c69-113">진행 `mdTypeRef` `mdModuleRef` 대상 멤버를 소유 하는 형식 또는 모듈의 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="b4c69-114">제한이 `mdMemberRef` 멤버 참조의 현재 범위에서 정의 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4c69-115">설명</span><span class="sxs-lookup"><span data-stu-id="b4c69-115">Remarks</span></span>  

 <span data-ttu-id="b4c69-116">메서드는로 지정 된 멤버를 조회 하 여 `DefineImportMember` `mbMember` 에 지정 된 다른 범위에 정의 되 `pImport` 고 해당 속성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="b4c69-117">이 정보를 사용 하 여 현재 범위에서 [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) 메서드를 호출 하 여 멤버 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="b4c69-118">일반적으로 메서드를 사용 하기 전에 `DefineImportMember` 현재 범위에서 대상 멤버의 부모 클래스, 인터페이스 또는 모듈에 대 한 형식 참조 또는 모듈 참조를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="b4c69-119">그런 다음이 참조에 대 한 메타 데이터 토큰이 인수에 전달 됩니다 `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="b4c69-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="b4c69-120">나중에 컴파일러나 링커를 통해 해결 될 경우 대상 멤버의 부모에 대 한 참조를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="b4c69-121">요약:</span><span class="sxs-lookup"><span data-stu-id="b4c69-121">To summarize:</span></span>  
  
- <span data-ttu-id="b4c69-122">대상 멤버가 필드 또는 메서드인 경우 [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) 또는 [IMetaDataEmit::D efineImportType](imetadataemit-defineimporttype-method.md) 메서드를 사용 하 여 현재 범위에서 멤버의 부모 클래스 또는 부모 인터페이스에 대 한 형식 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="b4c69-123">대상 멤버가 전역 변수나 전역 함수 (즉, 클래스 또는 인터페이스의 멤버가 아님) 인 경우 [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) 메서드를 사용 하 여 현재 범위에서 멤버의 부모 모듈에 대 한 모듈 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="b4c69-124">컴파일러 또는 링커가 대상 멤버의 부모를 나중에 확인 하는 경우를 전달 `mdTokenNil` `tkParent` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="b4c69-125">이를 적용 하는 유일한 시나리오는 현재 모듈에 연결 되 고 메타 데이터가 병합 되는 .obj 파일에서 전역 함수 또는 전역 변수를 가져오는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c69-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4c69-126">Requirements</span></span>  

 <span data-ttu-id="b4c69-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4c69-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c69-128">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b4c69-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4c69-129">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4c69-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4c69-130">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c69-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c69-131">참조</span><span class="sxs-lookup"><span data-stu-id="b4c69-131">See also</span></span>

- [<span data-ttu-id="b4c69-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4c69-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b4c69-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4c69-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
