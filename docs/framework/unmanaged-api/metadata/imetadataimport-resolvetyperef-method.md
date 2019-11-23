---
title: IMetaDataImport::ResolveTypeRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: 800b15bb75e74898cee9d838900ea14b60620940
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431478"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="66305-102">IMetaDataImport::ResolveTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="66305-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="66305-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span><span class="sxs-lookup"><span data-stu-id="66305-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66305-104">구문</span><span class="sxs-lookup"><span data-stu-id="66305-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66305-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66305-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="66305-106">[in] The TypeRef metadata token to return the referenced type information for.</span><span class="sxs-lookup"><span data-stu-id="66305-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="66305-107">[in] The IID of the interface to return in `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="66305-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="66305-108">Typically, this would be IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="66305-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="66305-109">[out] An interface to the module scope in which the referenced type is defined.</span><span class="sxs-lookup"><span data-stu-id="66305-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="66305-110">[out] A pointer to a TypeDef token that represents the referenced type.</span><span class="sxs-lookup"><span data-stu-id="66305-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66305-111">주의</span><span class="sxs-lookup"><span data-stu-id="66305-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="66305-112">Do not use this method if multiple application domains are loaded.</span><span class="sxs-lookup"><span data-stu-id="66305-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="66305-113">The method does not respect application domain boundaries.</span><span class="sxs-lookup"><span data-stu-id="66305-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="66305-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span><span class="sxs-lookup"><span data-stu-id="66305-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="66305-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span><span class="sxs-lookup"><span data-stu-id="66305-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="66305-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span><span class="sxs-lookup"><span data-stu-id="66305-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="66305-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="66305-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="66305-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span><span class="sxs-lookup"><span data-stu-id="66305-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66305-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66305-119">Requirements</span></span>  
 <span data-ttu-id="66305-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66305-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66305-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66305-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66305-122">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66305-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66305-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66305-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66305-124">참조</span><span class="sxs-lookup"><span data-stu-id="66305-124">See also</span></span>

- [<span data-ttu-id="66305-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66305-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="66305-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66305-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
