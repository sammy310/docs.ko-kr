---
title: IMetaDataEmit::DefinePermissionSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: 4e11a52c977de7796043868e80c147d8cfd1f506
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431577"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="8ebc8-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="8ebc8-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="8ebc8-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ebc8-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ebc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ebc8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="8ebc8-106">[in] The object to be decorated.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="8ebc8-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="8ebc8-108">[in] The permission BLOB.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="8ebc8-109">[in] The size, in bytes, of `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="8ebc8-110">[out] The returned permission token.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebc8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ebc8-111">Requirements</span></span>  
 <span data-ttu-id="8ebc8-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ebc8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebc8-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ebc8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ebc8-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ebc8-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ebc8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebc8-116">참조</span><span class="sxs-lookup"><span data-stu-id="8ebc8-116">See also</span></span>

- [<span data-ttu-id="8ebc8-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ebc8-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8ebc8-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ebc8-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
