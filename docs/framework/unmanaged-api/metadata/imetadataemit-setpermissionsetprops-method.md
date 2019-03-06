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
ms.openlocfilehash: 372d2fd62503969e47b5ab28528fa554ecd551ca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470109"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="a93a6-102">IMetaDataEmit::SetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a93a6-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="a93a6-103">설정 하거나 업데이트 기능에 대 한 이전 호출에서 정의 된 권한 집합의 메타 데이터 서명의 [imetadataemit:: Definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="a93a6-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a93a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a93a6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a93a6-106">[in] 데코 레이트 되어야 하는 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="a93a6-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 사용할 선언적 보안의 형식을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="a93a6-108">[in] BLOB 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="a93a6-109">[in] 크기 (바이트)의 `pvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="a93a6-110">[out] `mdPermission` 업데이트 된 사용 권한을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93a6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a93a6-111">Requirements</span></span>  
 <span data-ttu-id="a93a6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a93a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a93a6-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a93a6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a93a6-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a93a6-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a93a6-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a93a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93a6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a93a6-116">See also</span></span>
- [<span data-ttu-id="a93a6-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a93a6-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a93a6-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a93a6-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
