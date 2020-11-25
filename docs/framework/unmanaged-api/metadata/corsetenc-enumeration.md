---
title: CorSetENC 열거형
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705984"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="8a292-102">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="8a292-102">CorSetENC Enumeration</span></span>

<span data-ttu-id="8a292-103">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a292-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a292-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="8a292-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8a292-105">Members</span></span>  
  
|<span data-ttu-id="8a292-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8a292-106">Member</span></span>|<span data-ttu-id="8a292-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a292-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="8a292-108">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="8a292-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="8a292-110">메타 데이터를 업데이트할 수 있지만 토큰을 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="8a292-111">업데이트 중에 토큰을 이동할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="8a292-112">업데이트는 추가로만 구성 될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="8a292-113">토큰은 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="8a292-114">컴파일이 증분 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="8a292-115">변경 된 메타 데이터만 저장 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="8a292-116">`MDUpdateENC`에는, 및가 포함 됩니다 `MDUpdateFull` `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="8a292-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a292-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a292-117">Requirements</span></span>  

 <span data-ttu-id="8a292-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a292-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a292-119">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="8a292-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8a292-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a292-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a292-121">참조</span><span class="sxs-lookup"><span data-stu-id="8a292-121">See also</span></span>

- [<span data-ttu-id="8a292-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8a292-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
