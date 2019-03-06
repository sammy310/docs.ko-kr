---
title: IMetaDataImport::GetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466936"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="e0999-102">IMetaDataImport::GetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e0999-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="e0999-103">연관 된 메타 데이터를 가져옵니다는 <xref:System.Security.PermissionSet?displayProperty=nameWithType> 지정한 권한 토큰이 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="e0999-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0999-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0999-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0999-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0999-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="e0999-106">[in] 권한 집합에 대 한 메타 데이터 속성을 get을 나타내는 권한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e0999-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="e0999-107">[out] 사용 권한 집합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0999-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="e0999-108">[out] 권한 집합의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0999-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="e0999-109">[out] 크기 (바이트) `ppvPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0999-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0999-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0999-110">Requirements</span></span>  
 <span data-ttu-id="e0999-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0999-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0999-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0999-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0999-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e0999-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0999-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0999-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0999-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0999-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="e0999-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0999-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e0999-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0999-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
