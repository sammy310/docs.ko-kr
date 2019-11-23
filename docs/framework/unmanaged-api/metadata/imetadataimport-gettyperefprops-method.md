---
title: IMetaDataImport::GetTypeRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 6ea7605e062eb77e0488b3a9561c4d83be16fa7d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436704"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="a36e2-102">IMetaDataImport::GetTypeRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a36e2-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="a36e2-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span><span class="sxs-lookup"><span data-stu-id="a36e2-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a36e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a36e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a36e2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a36e2-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="a36e2-106">[in] The TypeRef token that represents the type to return metadata for.</span><span class="sxs-lookup"><span data-stu-id="a36e2-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="a36e2-107">[out] A pointer to the scope in which the reference is made.</span><span class="sxs-lookup"><span data-stu-id="a36e2-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="a36e2-108">This value is an AssemblyRef or ModuleRef token.</span><span class="sxs-lookup"><span data-stu-id="a36e2-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="a36e2-109">[out] A buffer containing the type name.</span><span class="sxs-lookup"><span data-stu-id="a36e2-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a36e2-110">[in] The requested size in wide characters of `szName`.</span><span class="sxs-lookup"><span data-stu-id="a36e2-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a36e2-111">[out] The returned size in wide characters of `szName`.</span><span class="sxs-lookup"><span data-stu-id="a36e2-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a36e2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a36e2-112">Requirements</span></span>  
 <span data-ttu-id="a36e2-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a36e2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a36e2-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a36e2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a36e2-115">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a36e2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a36e2-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a36e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36e2-117">참조</span><span class="sxs-lookup"><span data-stu-id="a36e2-117">See also</span></span>

- [<span data-ttu-id="a36e2-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a36e2-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a36e2-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a36e2-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
