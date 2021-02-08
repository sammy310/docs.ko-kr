---
description: '다음에 대 한 자세한 정보: CorGenericParamAttr 열거형'
title: CorGenericParamAttr 열거형
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: 8fe8cb20834ecbc5477bbe8b01bf77d6b1af0eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784459"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="b75ad-103">CorGenericParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="b75ad-103">CorGenericParamAttr Enumeration</span></span>

<span data-ttu-id="b75ad-104"><xref:System.Type> [IMetaDataEmit2::D efineGenericParam](imetadataemit2-definegenericparam-method.md)호출에 사용 되는 제네릭 형식에 대 한 매개 변수를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-104">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b75ad-105">구문</span><span class="sxs-lookup"><span data-stu-id="b75ad-105">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="b75ad-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b75ad-106">Members</span></span>  
  
|<span data-ttu-id="b75ad-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b75ad-107">Member</span></span>|<span data-ttu-id="b75ad-108">설명</span><span class="sxs-lookup"><span data-stu-id="b75ad-108">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="b75ad-109">매개 변수 분산은 인터페이스 및 대리자에 대 한 제네릭 매개 변수에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-109">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="b75ad-110">분산이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-110">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="b75ad-111">공 분산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-111">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="b75ad-112">반 공변성 (contravariance)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-112">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="b75ad-113">특수 제약 조건은 모든 매개 변수에 적용할 수 있습니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="b75ad-113">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="b75ad-114">매개 변수에 적용 되는 제약 조건이 없음을 나타냅니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="b75ad-114">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="b75ad-115"><xref:System.Type>매개 변수가 참조 형식 이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-115">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="b75ad-116"><xref:System.Type>매개 변수가 null 값이 될 수 없는 값 형식 이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-116">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="b75ad-117">매개 변수를 <xref:System.Type> 사용 하지 않는 기본 public 생성자가 매개 변수에 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b75ad-117">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b75ad-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b75ad-118">Requirements</span></span>  

 <span data-ttu-id="b75ad-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b75ad-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b75ad-120">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="b75ad-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b75ad-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b75ad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75ad-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b75ad-122">See also</span></span>

- [<span data-ttu-id="b75ad-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="b75ad-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
