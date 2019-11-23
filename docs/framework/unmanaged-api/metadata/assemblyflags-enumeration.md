---
title: AssemblyFlags 열거형
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444306"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="db9f3-102">AssemblyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="db9f3-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="db9f3-103">Contains values that describe run-time features of an assembly.</span><span class="sxs-lookup"><span data-stu-id="db9f3-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="db9f3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="db9f3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="db9f3-105">Members</span></span>  
  
|<span data-ttu-id="db9f3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="db9f3-106">Member</span></span>|<span data-ttu-id="db9f3-107">설명</span><span class="sxs-lookup"><span data-stu-id="db9f3-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="db9f3-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span><span class="sxs-lookup"><span data-stu-id="db9f3-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="db9f3-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span><span class="sxs-lookup"><span data-stu-id="db9f3-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="db9f3-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span><span class="sxs-lookup"><span data-stu-id="db9f3-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="db9f3-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span><span class="sxs-lookup"><span data-stu-id="db9f3-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="db9f3-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span><span class="sxs-lookup"><span data-stu-id="db9f3-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="db9f3-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span><span class="sxs-lookup"><span data-stu-id="db9f3-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="db9f3-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span><span class="sxs-lookup"><span data-stu-id="db9f3-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db9f3-115">주의</span><span class="sxs-lookup"><span data-stu-id="db9f3-115">Remarks</span></span>  
 <span data-ttu-id="db9f3-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="db9f3-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="db9f3-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span><span class="sxs-lookup"><span data-stu-id="db9f3-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db9f3-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db9f3-118">Requirements</span></span>  
 <span data-ttu-id="db9f3-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db9f3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db9f3-120">**Header:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db9f3-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="db9f3-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db9f3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db9f3-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db9f3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9f3-123">참조</span><span class="sxs-lookup"><span data-stu-id="db9f3-123">See also</span></span>

- [<span data-ttu-id="db9f3-124">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="db9f3-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="db9f3-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db9f3-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
