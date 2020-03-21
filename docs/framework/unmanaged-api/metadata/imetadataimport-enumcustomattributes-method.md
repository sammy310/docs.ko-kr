---
title: IMetaDataImport::EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175527"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="32e97-102">IMetaDataImport::EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="32e97-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="32e97-103">지정된 형식 또는 멤버와 연결된 사용자 지정 특성 정의 토큰을 연수합니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e97-104">구문</span><span class="sxs-lookup"><span data-stu-id="32e97-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e97-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32e97-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="32e97-106">【인, 아웃】 반환된 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="32e97-107">【인】 열거형 범위에 대한 토큰 또는 모든 사용자 지정 특성에 대한 0입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="32e97-108">【인】 등록할 특성 형식의 생성자 또는 `null` 모든 형식에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="32e97-109">【아웃】 사용자 지정 특성 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="32e97-110">[in] `rCustomAttributes` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="32e97-111">[아웃, 선택 사항] 에서 반환되는 실제 토큰 `rCustomAttributes`값 수입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32e97-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="32e97-112">Return Value</span></span>  
  
|<span data-ttu-id="32e97-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32e97-113">HRESULT</span></span>|<span data-ttu-id="32e97-114">Description</span><span class="sxs-lookup"><span data-stu-id="32e97-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="32e97-115">`EnumCustomAttributes`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="32e97-116">등록할 사용자 지정 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="32e97-117">이 경우 `pcCustomAttributes` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="32e97-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32e97-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32e97-118">Requirements</span></span>  
 <span data-ttu-id="32e97-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e97-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e97-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="32e97-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32e97-121">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="32e97-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32e97-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e97-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e97-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32e97-123">See also</span></span>

- [<span data-ttu-id="32e97-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32e97-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="32e97-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32e97-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
