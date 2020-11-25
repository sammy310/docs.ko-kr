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
ms.openlocfilehash: 788fd1815415bf8bcfa20d431a5451679d2025bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728279"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="e575e-102">IMetaDataImport::EnumModuleRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="e575e-102">IMetaDataImport::EnumModuleRefs Method</span></span>

<span data-ttu-id="e575e-103">가져온 모듈을 나타내는 ModuleRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e575e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e575e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e575e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e575e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e575e-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e575e-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="e575e-108">제한이 ModuleRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e575e-109">[in] `rModuleRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="e575e-110">제한이 에서 반환 된 ModuleRef 토큰의 수입니다 `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="e575e-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e575e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e575e-111">Return Value</span></span>  
  
|<span data-ttu-id="e575e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e575e-112">HRESULT</span></span>|<span data-ttu-id="e575e-113">설명</span><span class="sxs-lookup"><span data-stu-id="e575e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e575e-114">`EnumModuleRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e575e-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e575e-116">이 경우는 `pcModuleRefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e575e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e575e-117">Requirements</span></span>  

 <span data-ttu-id="e575e-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e575e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e575e-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e575e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e575e-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e575e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e575e-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e575e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e575e-122">참조</span><span class="sxs-lookup"><span data-stu-id="e575e-122">See also</span></span>

- [<span data-ttu-id="e575e-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e575e-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e575e-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e575e-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
