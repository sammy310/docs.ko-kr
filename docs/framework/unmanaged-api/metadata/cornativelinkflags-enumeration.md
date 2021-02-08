---
description: '자세히 알아보기: CorNativeLinkFlags 열거형'
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
ms.openlocfilehash: 9025d192ca92c1160c1b072b0dcfe045fa3ceab7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784355"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="a858a-103">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="a858a-103">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="a858a-104">네이티브 코드를 연결할 때 링커에서 사용하는 플래그 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a858a-104">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a858a-105">구문</span><span class="sxs-lookup"><span data-stu-id="a858a-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a858a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a858a-106">Members</span></span>  
  
|<span data-ttu-id="a858a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a858a-107">Member</span></span>|<span data-ttu-id="a858a-108">설명</span><span class="sxs-lookup"><span data-stu-id="a858a-108">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="a858a-109">플래그가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a858a-109">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="a858a-110">키워드를 나타냅니다 `setLastError` .</span><span class="sxs-lookup"><span data-stu-id="a858a-110">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="a858a-111">키워드를 나타냅니다 `nomangle` .</span><span class="sxs-lookup"><span data-stu-id="a858a-111">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="a858a-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a858a-112">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a858a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a858a-113">Requirements</span></span>  

 <span data-ttu-id="a858a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a858a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a858a-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a858a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a858a-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a858a-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a858a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a858a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a858a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a858a-118">See also</span></span>

- [<span data-ttu-id="a858a-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a858a-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
