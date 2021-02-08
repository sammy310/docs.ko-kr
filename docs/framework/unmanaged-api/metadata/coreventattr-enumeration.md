---
description: '자세한 정보: CorEventAttr 열거형'
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
ms.openlocfilehash: 70f05eacf2cc7c7975b9b52d402cceb60bbea426
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784511"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="0acec-103">CorEventAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="0acec-103">CorEventAttr Enumeration</span></span>

<span data-ttu-id="0acec-104">이벤트의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0acec-104">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0acec-105">구문</span><span class="sxs-lookup"><span data-stu-id="0acec-105">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="0acec-106">구성원</span><span class="sxs-lookup"><span data-stu-id="0acec-106">Members</span></span>  
  
|<span data-ttu-id="0acec-107">멤버</span><span class="sxs-lookup"><span data-stu-id="0acec-107">Member</span></span>|<span data-ttu-id="0acec-108">설명</span><span class="sxs-lookup"><span data-stu-id="0acec-108">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="0acec-109">이벤트를 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0acec-109">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="0acec-110">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0acec-110">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="0acec-111">공용 언어 런타임에서 이벤트 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0acec-111">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0acec-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0acec-112">Requirements</span></span>  

 <span data-ttu-id="0acec-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0acec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0acec-114">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="0acec-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0acec-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0acec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acec-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0acec-116">See also</span></span>

- [<span data-ttu-id="0acec-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="0acec-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
