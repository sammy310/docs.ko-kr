---
title: IMetaDataImport::EnumModuleRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d66d24da05bc3b8f0c3d0a828456d7c61613d219
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188313"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="9edc0-102">IMetaDataImport::EnumModuleRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="9edc0-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="9edc0-103">가져온 모듈을 나타내는 ModuleRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9edc0-104">구문</span><span class="sxs-lookup"><span data-stu-id="9edc0-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9edc0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9edc0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9edc0-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9edc0-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="9edc0-108">[out] ModuleRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9edc0-109">[in] `rModuleRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="9edc0-110">[out] ModuleRef 토큰에서 반환 된 수가 `rModuleRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9edc0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9edc0-111">Return Value</span></span>  
  
|<span data-ttu-id="9edc0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9edc0-112">HRESULT</span></span>|<span data-ttu-id="9edc0-113">설명</span><span class="sxs-lookup"><span data-stu-id="9edc0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9edc0-114">`EnumModuleRefs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9edc0-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9edc0-116">이런 경우 `pcModuleRefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9edc0-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9edc0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9edc0-117">Requirements</span></span>  
 <span data-ttu-id="9edc0-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9edc0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9edc0-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9edc0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9edc0-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9edc0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9edc0-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9edc0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9edc0-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="9edc0-122">See also</span></span>

- [<span data-ttu-id="9edc0-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9edc0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9edc0-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9edc0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
