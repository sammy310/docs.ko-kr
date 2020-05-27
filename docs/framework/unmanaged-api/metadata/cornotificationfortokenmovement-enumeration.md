---
title: CorNotificationForTokenMovement 열거형
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: e8065a5492884a4b7f5d662737e4beddc6fca5b3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007600"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="9735b-102">CorNotificationForTokenMovement 열거형</span><span class="sxs-lookup"><span data-stu-id="9735b-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="9735b-103">토큰 다시 매핑을 수행 하는 경우 메타 데이터 API 클라이언트에 전송 되는 알림을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9735b-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9735b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9735b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="9735b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9735b-105">Members</span></span>  
  
|<span data-ttu-id="9735b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9735b-106">Member</span></span>|<span data-ttu-id="9735b-107">설명</span><span class="sxs-lookup"><span data-stu-id="9735b-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="9735b-108">`mdTypeRef`, `mdMethodDef` , `mdMemberRef` 또는 `mdFieldDef` 토큰이 이동할 때 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9735b-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="9735b-109">토큰이 이동 하면 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9735b-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="9735b-110">토큰이 이동할 때 알리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9735b-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="9735b-111">토큰을 이동할 때 알립니다 `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="9735b-112">토큰을 이동할 때 알립니다 `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="9735b-113">토큰을 이동할 때 알립니다 `mdFieldDef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="9735b-114">토큰을 이동할 때 알립니다 `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="9735b-115">토큰을 이동할 때 알립니다 `mdTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="9735b-116">토큰을 이동할 때 알립니다 `mdParamDef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="9735b-117">토큰을 이동할 때 알립니다 `mdInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="9735b-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="9735b-118">토큰을 이동할 때 알립니다 `mdProperty` .</span><span class="sxs-lookup"><span data-stu-id="9735b-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="9735b-119">토큰을 이동할 때 알립니다 `mdEvent` .</span><span class="sxs-lookup"><span data-stu-id="9735b-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="9735b-120">토큰을 이동할 때 알립니다 `mdSignature` .</span><span class="sxs-lookup"><span data-stu-id="9735b-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="9735b-121">토큰을 이동할 때 알립니다 `mdTypeSpec` .</span><span class="sxs-lookup"><span data-stu-id="9735b-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="9735b-122">토큰을 이동할 때 알립니다 `mdCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="9735b-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="9735b-123">토큰을 이동할 때 알립니다 `mdSecurityValue` .</span><span class="sxs-lookup"><span data-stu-id="9735b-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="9735b-124">토큰을 이동할 때 알립니다 `mdPermission` .</span><span class="sxs-lookup"><span data-stu-id="9735b-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="9735b-125">토큰을 이동할 때 알립니다 `mdModuleRef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="9735b-126">토큰을 이동할 때 알립니다 `mdNameSpace` .</span><span class="sxs-lookup"><span data-stu-id="9735b-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="9735b-127">토큰을 이동할 때 알립니다 `mdAssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="9735b-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="9735b-128">토큰을 이동할 때 알립니다 `mdFile` .</span><span class="sxs-lookup"><span data-stu-id="9735b-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="9735b-129">토큰을 이동할 때 알립니다 `mdExportedType` .</span><span class="sxs-lookup"><span data-stu-id="9735b-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="9735b-130">토큰을 이동할 때 알립니다 `mdManifestResource` .</span><span class="sxs-lookup"><span data-stu-id="9735b-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9735b-131">설명</span><span class="sxs-lookup"><span data-stu-id="9735b-131">Remarks</span></span>  
 <span data-ttu-id="9735b-132">토큰은 메타 데이터 병합 중에 다시 매핑 (즉, 이동) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9735b-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9735b-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9735b-133">Requirements</span></span>  
 <span data-ttu-id="9735b-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9735b-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9735b-135">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="9735b-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9735b-136">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9735b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9735b-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9735b-137">See also</span></span>

- [<span data-ttu-id="9735b-138">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="9735b-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
