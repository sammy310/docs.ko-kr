---
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
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711600"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="57f10-102">IMetaDataImport::EnumFields 메서드</span><span class="sxs-lookup"><span data-stu-id="57f10-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="57f10-103">지정한 TypeDef 토큰이 참조하는 형식에 대한 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f10-104">구문</span><span class="sxs-lookup"><span data-stu-id="57f10-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57f10-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57f10-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="57f10-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="57f10-107">진행 해당 필드를 열거할 클래스의 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="57f10-108">제한이 FieldDef 토큰 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="57f10-109">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="57f10-110">제한이 에서 반환 되는 실제 FieldDef 토큰 수입니다 `rFields` .</span><span class="sxs-lookup"><span data-stu-id="57f10-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57f10-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="57f10-111">Return Value</span></span>  
  
|<span data-ttu-id="57f10-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57f10-112">HRESULT</span></span>|<span data-ttu-id="57f10-113">설명</span><span class="sxs-lookup"><span data-stu-id="57f10-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="57f10-114">`EnumFields` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="57f10-115">열거할 필드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-115">There are no fields to enumerate.</span></span> <span data-ttu-id="57f10-116">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57f10-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57f10-117">Requirements</span></span>  

 <span data-ttu-id="57f10-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57f10-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57f10-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="57f10-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57f10-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f10-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57f10-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57f10-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f10-122">참조</span><span class="sxs-lookup"><span data-stu-id="57f10-122">See also</span></span>

- [<span data-ttu-id="57f10-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57f10-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="57f10-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57f10-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
