---
title: CorManifestResourceFlags 열거형
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08f997e133fa6cc8769efe18e7ca06c0153f15a4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781805"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="3a7ed-102">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3a7ed-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="3a7ed-103">어셈블리 매니페스트에 인코딩된 리소스의 표시 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a7ed-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a7ed-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3a7ed-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3a7ed-105">Members</span></span>  
  
|<span data-ttu-id="3a7ed-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3a7ed-106">Member</span></span>|<span data-ttu-id="3a7ed-107">Description</span><span class="sxs-lookup"><span data-stu-id="3a7ed-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="3a7ed-108">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a7ed-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="3a7ed-109">리소스는 공용입니다.</span><span class="sxs-lookup"><span data-stu-id="3a7ed-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="3a7ed-110">리소스는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="3a7ed-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a7ed-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a7ed-111">Requirements</span></span>  
 <span data-ttu-id="3a7ed-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a7ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7ed-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3a7ed-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3a7ed-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7ed-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a7ed-115">See also</span></span>

- [<span data-ttu-id="3a7ed-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="3a7ed-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
