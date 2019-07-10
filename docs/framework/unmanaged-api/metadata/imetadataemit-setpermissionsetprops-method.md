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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77e6e9711f05262e494f2814750af8ef7cd9f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750895"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="7fea8-102">IMetaDataEmit::SetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7fea8-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="7fea8-103">설정 하거나 업데이트 기능에 대 한 이전 호출에서 정의 된 권한 집합의 메타 데이터 서명의 [imetadataemit:: Definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fea8-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fea8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fea8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fea8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7fea8-106">[in] 데코 레이트 되어야 하는 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="7fea8-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 사용할 선언적 보안의 형식을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="7fea8-108">[in] BLOB 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="7fea8-109">[in] 크기 (바이트)의 `pvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="7fea8-110">[out] `mdPermission` 업데이트 된 사용 권한을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7fea8-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fea8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fea8-111">Requirements</span></span>  
 <span data-ttu-id="7fea8-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fea8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fea8-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7fea8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fea8-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7fea8-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fea8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fea8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fea8-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fea8-116">See also</span></span>

- [<span data-ttu-id="7fea8-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fea8-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7fea8-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fea8-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
