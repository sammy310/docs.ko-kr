---
description: '자세히 알아보기: IMetaDataImport:: EnumFields 메서드'
title: IMetaDataImport::EnumFields 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 5cb9b3a47dc4c51b9eba24b9519e4b97846c1a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799384"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="81bf0-103">IMetaDataImport::EnumFields 메서드</span><span class="sxs-lookup"><span data-stu-id="81bf0-103">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="81bf0-104">지정한 TypeDef 토큰이 참조하는 형식에 대한 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-104">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81bf0-105">구문</span><span class="sxs-lookup"><span data-stu-id="81bf0-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81bf0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81bf0-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="81bf0-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="81bf0-108">진행 해당 필드를 열거할 클래스의 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-108">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="81bf0-109">제한이 FieldDef 토큰 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-109">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="81bf0-110">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="81bf0-111">제한이 에서 반환 되는 실제 FieldDef 토큰 수입니다 `rFields` .</span><span class="sxs-lookup"><span data-stu-id="81bf0-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81bf0-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="81bf0-112">Return Value</span></span>  
  
|<span data-ttu-id="81bf0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81bf0-113">HRESULT</span></span>|<span data-ttu-id="81bf0-114">설명</span><span class="sxs-lookup"><span data-stu-id="81bf0-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="81bf0-115">`EnumFields` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-115">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="81bf0-116">열거할 필드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-116">There are no fields to enumerate.</span></span> <span data-ttu-id="81bf0-117">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81bf0-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81bf0-118">Requirements</span></span>  

 <span data-ttu-id="81bf0-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81bf0-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81bf0-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="81bf0-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81bf0-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81bf0-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81bf0-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81bf0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bf0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81bf0-123">See also</span></span>

- [<span data-ttu-id="81bf0-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81bf0-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="81bf0-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81bf0-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
