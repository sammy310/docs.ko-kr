---
description: '다음에 대 한 자세한 정보: CorTokenType 열거형'
title: CorTokenType 열거형
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 954bddccd8fe20be46080f8843bcf754e0cf1bbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678408"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="573e1-103">CorTokenType 열거형</span><span class="sxs-lookup"><span data-stu-id="573e1-103">CorTokenType Enumeration</span></span>

<span data-ttu-id="573e1-104">메타 데이터 토큰의 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-104">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573e1-105">구문</span><span class="sxs-lookup"><span data-stu-id="573e1-105">Syntax</span></span>  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="573e1-106">구성원</span><span class="sxs-lookup"><span data-stu-id="573e1-106">Members</span></span>  
  
|<span data-ttu-id="573e1-107">멤버</span><span class="sxs-lookup"><span data-stu-id="573e1-107">Member</span></span>|<span data-ttu-id="573e1-108">설명</span><span class="sxs-lookup"><span data-stu-id="573e1-108">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="573e1-109">`mdModule`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-109">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="573e1-110">`mdTypeRef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-110">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="573e1-111">`mdTypeDef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-111">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="573e1-112">`mdFieldDef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-112">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="573e1-113">`mdMethodDef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-113">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="573e1-114">`mdParamDef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-114">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="573e1-115">`mdInterfaceImpl`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-115">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="573e1-116">`mdMemberRef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-116">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="573e1-117">`mdCustomAttribute`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-117">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="573e1-118">`mdPermission`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-118">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="573e1-119">`mdSignature`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-119">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="573e1-120">`mdEvent`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-120">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="573e1-121">`mdProperty`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-121">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="573e1-122">`mdModuleRef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-122">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="573e1-123">`mdTypeSpec`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-123">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="573e1-124">`mdAssembly`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-124">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="573e1-125">`mdAssemblyRef`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-125">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="573e1-126">`mdFile`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-126">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="573e1-127">`mdExportedType`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-127">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="573e1-128">`mdManifestResource`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-128">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="573e1-129">`mdGenericParam`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-129">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="573e1-130">`mdMethodSpec`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-130">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="573e1-131">`mdGenericParamConstraint`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-131">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="573e1-132">`mdString`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-132">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="573e1-133">`mdName`토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-133">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="573e1-134">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-134">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="573e1-135">설명</span><span class="sxs-lookup"><span data-stu-id="573e1-135">Remarks</span></span>  

 <span data-ttu-id="573e1-136">각 값은 해당 하는 메타 데이터 토큰에서 최상위 바이트의 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="573e1-136">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573e1-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="573e1-137">Requirements</span></span>  

 <span data-ttu-id="573e1-138">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="573e1-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="573e1-139">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="573e1-139">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="573e1-140">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="573e1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573e1-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="573e1-141">See also</span></span>

- [<span data-ttu-id="573e1-142">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="573e1-142">Metadata Enumerations</span></span>](metadata-enumerations.md)
