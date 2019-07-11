---
title: IMetaDataImport::EnumPermissionSets 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7d9874d4a609c353ae772b75a48af632bf4e85d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756535"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="82431-102">IMetaDataImport::EnumPermissionSets 메서드</span><span class="sxs-lookup"><span data-stu-id="82431-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="82431-103">지정한 메타데이터 범위의 개체에 대한 권한을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="82431-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82431-104">구문</span><span class="sxs-lookup"><span data-stu-id="82431-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82431-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82431-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="82431-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="82431-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82431-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="82431-108">[in] 가능한 가장 넓은 범위를 검색 하려면 NULL 검색의 범위를 제한 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="82431-109">[in] 나타내는 플래그를 <xref:System.Security.Permissions.SecurityAction> 에 포함할 값 `rPermission`, 또는 모든 작업을 반환 하는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="82431-110">[out] 권한 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="82431-111">[in] `rPermission` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="82431-112">[out] 권한이 토큰에서 반환 된 수가 `rPermission`합니다.</span><span class="sxs-lookup"><span data-stu-id="82431-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82431-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="82431-113">Return Value</span></span>  
  
|<span data-ttu-id="82431-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82431-114">HRESULT</span></span>|<span data-ttu-id="82431-115">Description</span><span class="sxs-lookup"><span data-stu-id="82431-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="82431-116">`EnumPermissionSets` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82431-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="82431-117">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82431-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="82431-118">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="82431-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82431-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82431-119">Requirements</span></span>  
 <span data-ttu-id="82431-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="82431-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82431-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82431-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82431-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="82431-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82431-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82431-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82431-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="82431-124">See also</span></span>

- [<span data-ttu-id="82431-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82431-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="82431-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82431-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
