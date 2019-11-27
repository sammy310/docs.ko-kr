---
title: CorArgType 열거형
ms.date: 03/30/2017
api_name:
- CorArgType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorArgType
helpviewer_keywords:
- CorArgType enumeration [.NET Framework metadata]
ms.assetid: 3c1cb268-57a0-4664-91c7-f6908ff29e32
topic_type:
- apiref
ms.openlocfilehash: 689295610006824be1107577c50376e79551cddc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444368"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="97ef5-102">CorArgType 열거형</span><span class="sxs-lookup"><span data-stu-id="97ef5-102">CorArgType Enumeration</span></span>
<span data-ttu-id="97ef5-103">런타임 핸들의 네이티브 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="97ef5-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ef5-104">구문</span><span class="sxs-lookup"><span data-stu-id="97ef5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorArgType {  
  
    IMAGE_CEE_CS_END        = 0x0,  
    IMAGE_CEE_CS_VOID       = 0x1,  
    IMAGE_CEE_CS_I4         = 0x2,  
    IMAGE_CEE_CS_I8         = 0x3,  
    IMAGE_CEE_CS_R4         = 0x4,  
    IMAGE_CEE_CS_R8         = 0x5,  
    IMAGE_CEE_CS_PTR        = 0x6,  
    IMAGE_CEE_CS_OBJECT     = 0x7,  
    IMAGE_CEE_CS_STRUCT4    = 0x8,  
    IMAGE_CEE_CS_STRUCT32   = 0x9,  
    IMAGE_CEE_CS_BYVALUE    = 0xA  
  
} CorArgType;  
```  
  
## <a name="requirements"></a><span data-ttu-id="97ef5-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97ef5-105">Requirements</span></span>  
 <span data-ttu-id="97ef5-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97ef5-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ef5-107">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="97ef5-107">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="97ef5-108">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ef5-108">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ef5-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97ef5-109">See also</span></span>

- [<span data-ttu-id="97ef5-110">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="97ef5-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
