---
description: '자세한 정보: CorSetENC 열거형'
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
ms.openlocfilehash: 5ba3e41c10b082ceb2ce7d327f7ff7f857ca98a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707399"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="81ab7-103">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="81ab7-103">CorSetENC Enumeration</span></span>

<span data-ttu-id="81ab7-104">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-104">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ab7-105">구문</span><span class="sxs-lookup"><span data-stu-id="81ab7-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="81ab7-106">구성원</span><span class="sxs-lookup"><span data-stu-id="81ab7-106">Members</span></span>  
  
|<span data-ttu-id="81ab7-107">멤버</span><span class="sxs-lookup"><span data-stu-id="81ab7-107">Member</span></span>|<span data-ttu-id="81ab7-108">설명</span><span class="sxs-lookup"><span data-stu-id="81ab7-108">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="81ab7-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-109">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="81ab7-110">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-110">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="81ab7-111">메타 데이터를 업데이트할 수 있지만 토큰을 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-111">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="81ab7-112">업데이트 중에 토큰을 이동할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-112">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="81ab7-113">업데이트는 추가로만 구성 될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-113">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="81ab7-114">토큰은 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-114">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="81ab7-115">컴파일이 증분 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-115">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="81ab7-116">변경 된 메타 데이터만 저장 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ab7-116">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="81ab7-117">`MDUpdateENC`에는, 및가 포함 됩니다 `MDUpdateFull` `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="81ab7-117">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81ab7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81ab7-118">Requirements</span></span>  

 <span data-ttu-id="81ab7-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81ab7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ab7-120">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="81ab7-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="81ab7-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ab7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ab7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81ab7-122">See also</span></span>

- [<span data-ttu-id="81ab7-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="81ab7-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
