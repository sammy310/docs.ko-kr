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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fb70d530af24798636972de0a4d6280dbcb8f1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781635"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="d725b-102">CorPropertyAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="d725b-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="d725b-103">속성의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d725b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d725b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d725b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d725b-105">Members</span></span>  
  
|<span data-ttu-id="d725b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d725b-106">Member</span></span>|<span data-ttu-id="d725b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d725b-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="d725b-108">속성이 특별 하 고 이름과 설명 하는지 지정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="d725b-109">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="d725b-110">공용 언어 런타임 메타 데이터 내부 Api 인코딩을 확인 하도록 속성 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="d725b-111">속성 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="d725b-112">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d725b-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d725b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d725b-113">Requirements</span></span>  
 <span data-ttu-id="d725b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d725b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d725b-115">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d725b-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d725b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d725b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d725b-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="d725b-117">See also</span></span>

- [<span data-ttu-id="d725b-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d725b-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
