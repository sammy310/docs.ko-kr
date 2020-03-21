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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176190"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="306ec-102">CorCheckDuplicatesFor 열거형</span><span class="sxs-lookup"><span data-stu-id="306ec-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="306ec-103">중복을 검사할 메타데이터 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="306ec-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="306ec-105">구성원</span><span class="sxs-lookup"><span data-stu-id="306ec-105">Members</span></span>  
  
|<span data-ttu-id="306ec-106">멤버</span><span class="sxs-lookup"><span data-stu-id="306ec-106">Member</span></span>|<span data-ttu-id="306ec-107">Description</span><span class="sxs-lookup"><span data-stu-id="306ec-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="306ec-108">모든 메타데이터 토큰에 중복이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="306ec-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="306ec-110">메타데이터 토큰에 중복이 있는지 확인하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="306ec-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="306ec-111">토큰의 `mdTypeDef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="306ec-112">토큰의 `mdInterfaceImpl` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="306ec-113">토큰의 `mdMethodDef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="306ec-114">토큰의 `mdTypeRef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="306ec-115">토큰의 `mdMemberRef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="306ec-116">토큰의 `mdCustomAttribute` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="306ec-117">토큰의 `mdParamDef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="306ec-118">토큰의 `mdPermission` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="306ec-119">토큰의 `mdProperty` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="306ec-120">토큰의 `mdEvent` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="306ec-121">토큰의 `mdFieldDef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="306ec-122">토큰의 `mdSignature` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="306ec-123">토큰의 `mdModuleRef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="306ec-124">토큰의 `mdTypeSpec` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="306ec-125">토큰의 `mdImplMap` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="306ec-126">토큰의 `mdAssemblyRef` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="306ec-127">토큰의 `mdFile` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="306ec-128">토큰의 `mdExportedType` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="306ec-129">토큰의 `mdManifestResource` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="306ec-130">토큰의 `mdGenericParam` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="306ec-131">토큰의 `mdMethodSpec` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="306ec-132">토큰의 `mdGenericParamConstraint` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="306ec-133">토큰의 `mdAssembly` 중복을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="306ec-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="306ec-134">및 `mdMemberRef` `mdTypeRef` `mdMethodSpec` 토큰의 중복을 확인합니다. `mdSignature` `mdTypeSpec`</span><span class="sxs-lookup"><span data-stu-id="306ec-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="306ec-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="306ec-135">Requirements</span></span>  
 <span data-ttu-id="306ec-136">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="306ec-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306ec-137">**헤더:** 코르Hdr.h</span><span class="sxs-lookup"><span data-stu-id="306ec-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="306ec-138">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306ec-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306ec-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="306ec-139">See also</span></span>

- [<span data-ttu-id="306ec-140">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="306ec-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
