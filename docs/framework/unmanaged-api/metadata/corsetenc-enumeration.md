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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2796be32154275387da891683cc5053095f534af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772319"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="5f8e2-102">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="5f8e2-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="5f8e2-103">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f8e2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5f8e2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5f8e2-105">Members</span></span>  
  
|<span data-ttu-id="5f8e2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5f8e2-106">Member</span></span>|<span data-ttu-id="5f8e2-107">Description</span><span class="sxs-lookup"><span data-stu-id="5f8e2-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="5f8e2-108">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="5f8e2-109">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="5f8e2-110">메타 데이터를 업데이트할 수 있지만 토큰은 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="5f8e2-111">업데이트 하는 동안 토큰을 이동할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="5f8e2-112">업데이트 추가 이루어진 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="5f8e2-113">토큰을 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="5f8e2-114">증분 컴파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="5f8e2-115">해당만 변경 된 메타 데이터를 저장할 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="5f8e2-116">포함 `MDUpdateENC`하십시오 `MDUpdateFull` 및 `MDUpdateIncremental`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f8e2-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f8e2-117">Requirements</span></span>  
 <span data-ttu-id="5f8e2-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8e2-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5f8e2-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5f8e2-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8e2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8e2-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f8e2-121">See also</span></span>

- [<span data-ttu-id="5f8e2-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="5f8e2-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
