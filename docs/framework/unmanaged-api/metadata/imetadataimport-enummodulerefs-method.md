---
description: '자세히 알아보기: IMetaDataImport:: EnumModuleRefs 메서드'
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
ms.openlocfilehash: 3e12d3da8ff556cb3add73ade77e11a68bf60223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688821"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="8e436-103">IMetaDataImport::EnumModuleRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="8e436-103">IMetaDataImport::EnumModuleRefs Method</span></span>

<span data-ttu-id="8e436-104">가져온 모듈을 나타내는 ModuleRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-104">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e436-105">구문</span><span class="sxs-lookup"><span data-stu-id="8e436-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e436-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e436-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="8e436-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8e436-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-108">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="8e436-109">제한이 ModuleRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-109">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8e436-110">[in] `rModuleRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-110">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="8e436-111">제한이 에서 반환 된 ModuleRef 토큰의 수입니다 `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="8e436-111">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e436-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="8e436-112">Return Value</span></span>  
  
|<span data-ttu-id="8e436-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e436-113">HRESULT</span></span>|<span data-ttu-id="8e436-114">설명</span><span class="sxs-lookup"><span data-stu-id="8e436-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8e436-115">`EnumModuleRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-115">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8e436-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="8e436-117">이 경우는 `pcModuleRefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-117">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e436-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e436-118">Requirements</span></span>  

 <span data-ttu-id="8e436-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e436-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e436-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8e436-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e436-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e436-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e436-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e436-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e436-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e436-123">See also</span></span>

- [<span data-ttu-id="8e436-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e436-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8e436-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e436-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
