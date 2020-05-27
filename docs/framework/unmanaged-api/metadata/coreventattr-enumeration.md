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
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007441"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="eb797-102">CorEventAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="eb797-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="eb797-103">이벤트의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eb797-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb797-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb797-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="eb797-105">멤버</span><span class="sxs-lookup"><span data-stu-id="eb797-105">Members</span></span>  
  
|<span data-ttu-id="eb797-106">멤버</span><span class="sxs-lookup"><span data-stu-id="eb797-106">Member</span></span>|<span data-ttu-id="eb797-107">설명</span><span class="sxs-lookup"><span data-stu-id="eb797-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="eb797-108">이벤트를 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb797-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="eb797-109">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb797-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="eb797-110">공용 언어 런타임에서 이벤트 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb797-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb797-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb797-111">Requirements</span></span>  
 <span data-ttu-id="eb797-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb797-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb797-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="eb797-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="eb797-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb797-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb797-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb797-115">See also</span></span>

- [<span data-ttu-id="eb797-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="eb797-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
