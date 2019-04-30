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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045796"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="f9bb4-102">CorGenericParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="f9bb4-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="f9bb4-103">설명 하는 값을 포함 합니다 <xref:System.Type> 호출에서 사용된 된 제네릭 형식에 대 한 매개 변수 [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9bb4-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9bb4-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="f9bb4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f9bb4-105">Members</span></span>  
  
|<span data-ttu-id="f9bb4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f9bb4-106">Member</span></span>|<span data-ttu-id="f9bb4-107">설명</span><span class="sxs-lookup"><span data-stu-id="f9bb4-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="f9bb4-108">매개 변수 분산 인터페이스 및 대리자에 제네릭 매개 변수에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="f9bb4-109">분산이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="f9bb4-110">공변성 (covariance)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="f9bb4-111">반 공변성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="f9bb4-112">모든 특수 제약 조건을 적용할 수 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="f9bb4-113">제약 조건이 없는 적용 된다고 합니다 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="f9bb4-114">나타내는 <xref:System.Type> 매개 변수는 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="f9bb4-115">나타내는 <xref:System.Type> 매개 변수는 null 값을 사용할 수 없는 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="f9bb4-116">나타내는 <xref:System.Type> 매개 변수는 매개 변수가 없는 기본 public 생성자를 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9bb4-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9bb4-117">Requirements</span></span>  
 <span data-ttu-id="f9bb4-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9bb4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9bb4-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f9bb4-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f9bb4-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9bb4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bb4-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="f9bb4-121">See also</span></span>

- [<span data-ttu-id="f9bb4-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f9bb4-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
