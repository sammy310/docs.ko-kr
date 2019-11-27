---
title: CorNativeLinkFlags 열거형
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: 1362efbf518310240ce665badc93810d1c0b9b89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450194"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="cd976-102">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="cd976-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="cd976-103">네이티브 코드를 연결할 때 링커에서 사용하는 플래그 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd976-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd976-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cd976-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cd976-105">Members</span></span>  
  
|<span data-ttu-id="cd976-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cd976-106">Member</span></span>|<span data-ttu-id="cd976-107">설명</span><span class="sxs-lookup"><span data-stu-id="cd976-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="cd976-108">플래그가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="cd976-109">`setLastError` 키워드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="cd976-110">`nomangle` 키워드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="cd976-111">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd976-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd976-112">Requirements</span></span>  
 <span data-ttu-id="cd976-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd976-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd976-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="cd976-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd976-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd976-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd976-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd976-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd976-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd976-117">See also</span></span>

- [<span data-ttu-id="cd976-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="cd976-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
