---
title: IMetaDataImport::FindTypeRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 21a69d120cc732ca6659f77abc9f8ea0c993271e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437792"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="923fb-102">IMetaDataImport::FindTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="923fb-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="923fb-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span><span class="sxs-lookup"><span data-stu-id="923fb-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="923fb-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="923fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="923fb-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="923fb-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span><span class="sxs-lookup"><span data-stu-id="923fb-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="923fb-107">[in] The name of the type reference to search for.</span><span class="sxs-lookup"><span data-stu-id="923fb-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="923fb-108">[out] A pointer to the matching TypeRef token.</span><span class="sxs-lookup"><span data-stu-id="923fb-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923fb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="923fb-109">Requirements</span></span>  
 <span data-ttu-id="923fb-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="923fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923fb-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="923fb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="923fb-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="923fb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="923fb-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923fb-114">참조</span><span class="sxs-lookup"><span data-stu-id="923fb-114">See also</span></span>

- [<span data-ttu-id="923fb-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923fb-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="923fb-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923fb-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
