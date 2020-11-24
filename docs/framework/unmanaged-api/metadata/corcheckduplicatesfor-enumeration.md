---
title: CorCheckDuplicatesFor 열거형
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 4acdfd6df410f229a002fa191ef24766748a1262
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672359"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="d4e88-102">CorCheckDuplicatesFor 열거형</span><span class="sxs-lookup"><span data-stu-id="d4e88-102">CorCheckDuplicatesFor Enumeration</span></span>

<span data-ttu-id="d4e88-103">중복을 확인할 메타 데이터 토큰을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e88-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4e88-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="d4e88-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d4e88-105">Members</span></span>  
  
|<span data-ttu-id="d4e88-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d4e88-106">Member</span></span>|<span data-ttu-id="d4e88-107">설명</span><span class="sxs-lookup"><span data-stu-id="d4e88-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="d4e88-108">모든 메타 데이터 토큰에 중복 항목이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="d4e88-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="d4e88-110">메타 데이터 토큰에서 중복 항목을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="d4e88-111">토큰의 중복을 확인 `mdTypeDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="d4e88-112">토큰의 중복을 확인 `mdInterfaceImpl` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="d4e88-113">토큰의 중복을 확인 `mdMethodDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="d4e88-114">토큰의 중복을 확인 `mdTypeRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="d4e88-115">토큰의 중복을 확인 `mdMemberRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="d4e88-116">토큰의 중복을 확인 `mdCustomAttribute` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="d4e88-117">토큰의 중복을 확인 `mdParamDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="d4e88-118">토큰의 중복을 확인 `mdPermission` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="d4e88-119">토큰의 중복을 확인 `mdProperty` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="d4e88-120">토큰의 중복을 확인 `mdEvent` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="d4e88-121">토큰의 중복을 확인 `mdFieldDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="d4e88-122">토큰의 중복을 확인 `mdSignature` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="d4e88-123">토큰의 중복을 확인 `mdModuleRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="d4e88-124">토큰의 중복을 확인 `mdTypeSpec` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="d4e88-125">토큰의 중복을 확인 `mdImplMap` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="d4e88-126">토큰의 중복을 확인 `mdAssemblyRef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="d4e88-127">토큰의 중복을 확인 `mdFile` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="d4e88-128">토큰의 중복을 확인 `mdExportedType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="d4e88-129">토큰의 중복을 확인 `mdManifestResource` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="d4e88-130">토큰의 중복을 확인 `mdGenericParam` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="d4e88-131">토큰의 중복을 확인 `mdMethodSpec` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="d4e88-132">토큰의 중복을 확인 `mdGenericParamConstraint` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="d4e88-133">토큰의 중복을 확인 `mdAssembly` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="d4e88-134">`mdMemberRef`,, `mdTypeRef` `mdSignature` , 및 토큰이 중복 되는지 확인 `mdTypeSpec` `mdMethodSpec` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e88-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4e88-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4e88-135">Requirements</span></span>  

 <span data-ttu-id="d4e88-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4e88-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4e88-137">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="d4e88-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d4e88-138">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4e88-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e88-139">참조</span><span class="sxs-lookup"><span data-stu-id="d4e88-139">See also</span></span>

- [<span data-ttu-id="d4e88-140">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d4e88-140">Metadata Enumerations</span></span>](metadata-enumerations.md)
