---
title: CorEventAttr 열거형
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: ec2972605c40f4ba292f5a5f58d6d3efed53f966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443565"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="571d5-102">CorEventAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="571d5-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="571d5-103">이벤트의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="571d5-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="571d5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="571d5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="571d5-105">Members</span></span>  
  
|<span data-ttu-id="571d5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="571d5-106">Member</span></span>|<span data-ttu-id="571d5-107">설명</span><span class="sxs-lookup"><span data-stu-id="571d5-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="571d5-108">Specifies that the event is special, and that its name describes how.</span><span class="sxs-lookup"><span data-stu-id="571d5-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="571d5-109">Reserved for internal use by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="571d5-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="571d5-110">Specifies that the common language runtime should check the encoding of the event name.</span><span class="sxs-lookup"><span data-stu-id="571d5-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="571d5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="571d5-111">Requirements</span></span>  
 <span data-ttu-id="571d5-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="571d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="571d5-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="571d5-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="571d5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571d5-115">참조</span><span class="sxs-lookup"><span data-stu-id="571d5-115">See also</span></span>

- [<span data-ttu-id="571d5-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="571d5-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
