---
title: IMetaDataImport::FindTypeDefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
ms.openlocfilehash: b1b1c557eea62cae6d2ad09303441e4635abc899
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437845"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="7f781-102">IMetaDataImport::FindTypeDefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="7f781-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="7f781-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span><span class="sxs-lookup"><span data-stu-id="7f781-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f781-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f781-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f781-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f781-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="7f781-106">[in] The name of the type for which to get the TypeDef token.</span><span class="sxs-lookup"><span data-stu-id="7f781-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="7f781-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span><span class="sxs-lookup"><span data-stu-id="7f781-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="7f781-108">If the type to find is not a nested class, set this value to NULL.</span><span class="sxs-lookup"><span data-stu-id="7f781-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7f781-109">[out] A pointer to the matching TypeDef token.</span><span class="sxs-lookup"><span data-stu-id="7f781-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f781-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f781-110">Requirements</span></span>  
 <span data-ttu-id="7f781-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f781-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f781-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f781-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f781-113">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f781-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f781-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f781-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f781-115">참조</span><span class="sxs-lookup"><span data-stu-id="7f781-115">See also</span></span>

- [<span data-ttu-id="7f781-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f781-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7f781-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f781-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
