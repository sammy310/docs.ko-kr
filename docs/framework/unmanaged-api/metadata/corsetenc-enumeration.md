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
ms.openlocfilehash: 39f72e670ddc700c257f50f6bad6fab702ec21b6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432767"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="a60dc-102">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="a60dc-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="a60dc-103">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a60dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="a60dc-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a60dc-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a60dc-105">Members</span></span>  
  
|<span data-ttu-id="a60dc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a60dc-106">Member</span></span>|<span data-ttu-id="a60dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="a60dc-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="a60dc-108">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="a60dc-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="a60dc-110">메타 데이터를 업데이트할 수 있지만 토큰을 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="a60dc-111">업데이트 중에 토큰을 이동할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="a60dc-112">업데이트는 추가로만 구성 될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="a60dc-113">토큰은 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="a60dc-114">컴파일이 증분 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="a60dc-115">변경 된 메타 데이터만 저장 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="a60dc-116">`MDUpdateENC`, `MDUpdateFull` 및 `MDUpdateIncremental`를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60dc-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a60dc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a60dc-117">Requirements</span></span>  
 <span data-ttu-id="a60dc-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a60dc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a60dc-119">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="a60dc-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a60dc-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a60dc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60dc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a60dc-121">See also</span></span>

- [<span data-ttu-id="a60dc-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a60dc-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
