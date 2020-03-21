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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176177"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="f4316-102">CorGenericParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="f4316-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="f4316-103"><xref:System.Type> [IMetaDataEmit2::DefineGenericParam에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)대한 호출에 사용되는 제네릭 형식에 대한 매개 변수를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4316-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4316-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f4316-105">구성원</span><span class="sxs-lookup"><span data-stu-id="f4316-105">Members</span></span>  
  
|<span data-ttu-id="f4316-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f4316-106">Member</span></span>|<span data-ttu-id="f4316-107">Description</span><span class="sxs-lookup"><span data-stu-id="f4316-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="f4316-108">매개 변수 분산은 인터페이스 및 대리자에 대한 일반 매개 변수에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="f4316-109">분산이 없는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="f4316-110">공분산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="f4316-111">모순을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="f4316-112">특수 제약 조건은 <xref:System.Type> 모든 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="f4316-113">매개 변수에 제약 <xref:System.Type> 조건이 적용되지 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="f4316-114">매개 변수가 <xref:System.Type> 참조 형식이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="f4316-115">매개 변수는 <xref:System.Type> null 값이 될 수 없는 값 형식이어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="f4316-116">매개 변수에는 <xref:System.Type> 매개 변수를 수행하지 않는 기본 공용 생성자가 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4316-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4316-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4316-117">Requirements</span></span>  
 <span data-ttu-id="f4316-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4316-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4316-119">**헤더:** 코르Hdr.h</span><span class="sxs-lookup"><span data-stu-id="f4316-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f4316-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4316-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4316-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4316-121">See also</span></span>

- [<span data-ttu-id="f4316-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f4316-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
