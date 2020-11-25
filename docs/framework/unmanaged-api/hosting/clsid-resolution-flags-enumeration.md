---
title: CLSID_RESOLUTION_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706166"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="78064-102">CLSID_RESOLUTION_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="78064-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="78064-103">CLR (공용 언어 런타임)에서를 확인 하는 방법을 나타내는 값을 포함 합니다 `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="78064-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78064-104">구문</span><span class="sxs-lookup"><span data-stu-id="78064-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="78064-105">멤버</span><span class="sxs-lookup"><span data-stu-id="78064-105">Members</span></span>  
  
|<span data-ttu-id="78064-106">멤버</span><span class="sxs-lookup"><span data-stu-id="78064-106">Member</span></span>|<span data-ttu-id="78064-107">설명</span><span class="sxs-lookup"><span data-stu-id="78064-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="78064-108">기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78064-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="78064-109">런타임이 레지스트리를 검색 하 고 shim 정책을 적용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78064-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78064-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78064-110">Requirements</span></span>  

 <span data-ttu-id="78064-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78064-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78064-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="78064-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78064-113">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78064-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78064-114">참조</span><span class="sxs-lookup"><span data-stu-id="78064-114">See also</span></span>

- [<span data-ttu-id="78064-115">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="78064-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
