---
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
ms.openlocfilehash: ea50430c3ae6cef9b47880bcb8ad969f62ce9c39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704918"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="82f7d-102">CorGenericParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="82f7d-102">CorGenericParamAttr Enumeration</span></span>

<span data-ttu-id="82f7d-103"><xref:System.Type> [IMetaDataEmit2::D efineGenericParam](imetadataemit2-definegenericparam-method.md)호출에 사용 되는 제네릭 형식에 대 한 매개 변수를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="82f7d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="82f7d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="82f7d-105">Members</span></span>  
  
|<span data-ttu-id="82f7d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="82f7d-106">Member</span></span>|<span data-ttu-id="82f7d-107">설명</span><span class="sxs-lookup"><span data-stu-id="82f7d-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="82f7d-108">매개 변수 분산은 인터페이스 및 대리자에 대 한 제네릭 매개 변수에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="82f7d-109">분산이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="82f7d-110">공 분산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="82f7d-111">반 공변성 (contravariance)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="82f7d-112">특수 제약 조건은 모든 매개 변수에 적용할 수 있습니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="82f7d-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="82f7d-113">매개 변수에 적용 되는 제약 조건이 없음을 나타냅니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="82f7d-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="82f7d-114"><xref:System.Type>매개 변수가 참조 형식 이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="82f7d-115"><xref:System.Type>매개 변수가 null 값이 될 수 없는 값 형식 이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="82f7d-116">매개 변수를 <xref:System.Type> 사용 하지 않는 기본 public 생성자가 매개 변수에 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f7d-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82f7d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82f7d-117">Requirements</span></span>  

 <span data-ttu-id="82f7d-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82f7d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f7d-119">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="82f7d-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="82f7d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f7d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f7d-121">참조</span><span class="sxs-lookup"><span data-stu-id="82f7d-121">See also</span></span>

- [<span data-ttu-id="82f7d-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="82f7d-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
