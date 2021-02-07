---
description: '자세히 알아보기: IMetaDataImport2:: GetGenericParamConstraintProps 메서드'
title: IMetaDataImport2::GetGenericParamConstraintProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
ms.openlocfilehash: 03cc4df655f9ab7a1c04840e9d4fa782a90ce1ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688743"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="24acf-103">IMetaDataImport2::GetGenericParamConstraintProps 메서드</span><span class="sxs-lookup"><span data-stu-id="24acf-103">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>

<span data-ttu-id="24acf-104">지정 된 제약 조건 토큰이 나타내는 제네릭 매개 변수 제약 조건과 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24acf-104">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24acf-105">구문</span><span class="sxs-lookup"><span data-stu-id="24acf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24acf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24acf-106">Parameters</span></span>  

 `gpc`  
 <span data-ttu-id="24acf-107">진행 메타 데이터를 반환할 제네릭 매개 변수 제약 조건에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="24acf-107">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="24acf-108">제한이 제약 조건이 있는 제네릭 매개 변수를 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24acf-108">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="24acf-109">제한이 에 대 한 제약 조건을 나타내는 TypeDef, TypeRef 또는 TypeSpec 토큰에 대 한 포인터입니다 `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="24acf-109">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24acf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24acf-110">Requirements</span></span>  

 <span data-ttu-id="24acf-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24acf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24acf-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="24acf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24acf-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24acf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24acf-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24acf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24acf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24acf-115">See also</span></span>

- [<span data-ttu-id="24acf-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24acf-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="24acf-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24acf-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
