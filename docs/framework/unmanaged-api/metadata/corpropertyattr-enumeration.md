---
title: CorPropertyAttr 열거형
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: d76de80f87a8e5a63eac9f6a413f2efb0e394b0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706127"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="8a9e5-102">CorPropertyAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="8a9e5-102">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="8a9e5-103">속성의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a9e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a9e5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="8a9e5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8a9e5-105">Members</span></span>  
  
|<span data-ttu-id="8a9e5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8a9e5-106">Member</span></span>|<span data-ttu-id="8a9e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a9e5-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="8a9e5-108">속성을 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="8a9e5-109">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="8a9e5-110">공용 언어 런타임 메타 데이터 내부 Api가 속성 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="8a9e5-111">속성이 기본값을 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="8a9e5-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a9e5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a9e5-113">Requirements</span></span>  

 <span data-ttu-id="8a9e5-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a9e5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a9e5-115">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="8a9e5-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8a9e5-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a9e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9e5-117">참조</span><span class="sxs-lookup"><span data-stu-id="8a9e5-117">See also</span></span>

- [<span data-ttu-id="8a9e5-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8a9e5-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
