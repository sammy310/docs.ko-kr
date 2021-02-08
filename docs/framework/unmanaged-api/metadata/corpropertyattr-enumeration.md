---
description: '자세한 정보: CorPropertyAttr 열거형'
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
ms.openlocfilehash: 1f3e2fccb11a067c6c46350a2c36d47007875755
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784238"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="b61ab-103">CorPropertyAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="b61ab-103">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="b61ab-104">속성의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-104">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="b61ab-105">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="b61ab-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b61ab-106">Members</span></span>  
  
|<span data-ttu-id="b61ab-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b61ab-107">Member</span></span>|<span data-ttu-id="b61ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="b61ab-108">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="b61ab-109">속성을 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-109">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="b61ab-110">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-110">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="b61ab-111">공용 언어 런타임 메타 데이터 내부 Api가 속성 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-111">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="b61ab-112">속성이 기본값을 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-112">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="b61ab-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b61ab-113">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b61ab-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b61ab-114">Requirements</span></span>  

 <span data-ttu-id="b61ab-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b61ab-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b61ab-116">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="b61ab-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b61ab-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b61ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61ab-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b61ab-118">See also</span></span>

- [<span data-ttu-id="b61ab-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="b61ab-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
