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
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177940"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="154ba-102">CorPropertyAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="154ba-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="154ba-103">속성의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="154ba-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="154ba-105">구성원</span><span class="sxs-lookup"><span data-stu-id="154ba-105">Members</span></span>  
  
|<span data-ttu-id="154ba-106">멤버</span><span class="sxs-lookup"><span data-stu-id="154ba-106">Member</span></span>|<span data-ttu-id="154ba-107">Description</span><span class="sxs-lookup"><span data-stu-id="154ba-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="154ba-108">속성이 특수하고 해당 이름이 방법을 설명한다는 것을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="154ba-109">공통 언어 런타임에서 내부 용으로 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="154ba-110">공통 언어 런타임 메타데이터 내부 API가 속성 이름의 인코딩을 확인해야 한다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="154ba-111">속성이 기본값을 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="154ba-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="154ba-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="154ba-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="154ba-113">Requirements</span></span>  
 <span data-ttu-id="154ba-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="154ba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154ba-115">**헤더:** 코르Hdr.h</span><span class="sxs-lookup"><span data-stu-id="154ba-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="154ba-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154ba-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="154ba-117">See also</span></span>

- [<span data-ttu-id="154ba-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="154ba-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
