---
title: IMetaDataEmit::SetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 53a75b8e7edd15cd233577e0a3714fb5d981495f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432333"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="5803b-102">IMetaDataEmit::SetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5803b-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="5803b-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5803b-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5803b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5803b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5803b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5803b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5803b-106">[in] A metadata token that represents the object to be decorated.</span><span class="sxs-lookup"><span data-stu-id="5803b-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="5803b-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span><span class="sxs-lookup"><span data-stu-id="5803b-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="5803b-108">[in] The permission BLOB.</span><span class="sxs-lookup"><span data-stu-id="5803b-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="5803b-109">[in] The size, in bytes, of `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="5803b-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="5803b-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span><span class="sxs-lookup"><span data-stu-id="5803b-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5803b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5803b-111">Requirements</span></span>  
 <span data-ttu-id="5803b-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5803b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5803b-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5803b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5803b-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5803b-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5803b-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5803b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5803b-116">참조</span><span class="sxs-lookup"><span data-stu-id="5803b-116">See also</span></span>

- [<span data-ttu-id="5803b-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5803b-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5803b-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5803b-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
