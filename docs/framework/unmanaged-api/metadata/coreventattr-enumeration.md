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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7562ec10b6822ae0ec1478cdb077578493ea0b7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781875"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="9ebd9-102">CorEventAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="9ebd9-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="9ebd9-103">이벤트의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebd9-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ebd9-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ebd9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9ebd9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9ebd9-105">Members</span></span>  
  
|<span data-ttu-id="9ebd9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9ebd9-106">Member</span></span>|<span data-ttu-id="9ebd9-107">설명</span><span class="sxs-lookup"><span data-stu-id="9ebd9-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="9ebd9-108">이벤트는 특별 하 고 이름과 설명 하는지 지정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9ebd9-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="9ebd9-109">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ebd9-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="9ebd9-110">공용 언어 런타임 이벤트 이름 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ebd9-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ebd9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ebd9-111">Requirements</span></span>  
 <span data-ttu-id="9ebd9-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ebd9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ebd9-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9ebd9-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9ebd9-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ebd9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ebd9-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ebd9-115">See also</span></span>

- [<span data-ttu-id="9ebd9-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="9ebd9-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
