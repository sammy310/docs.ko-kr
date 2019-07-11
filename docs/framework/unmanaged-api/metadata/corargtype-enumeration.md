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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ae7b61d056c08691e19e639353b6ab6fb8443c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780938"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="ee220-102">CorArgType 열거형</span><span class="sxs-lookup"><span data-stu-id="ee220-102">CorArgType Enumeration</span></span>
<span data-ttu-id="ee220-103">런타임 핸들의 네이티브 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee220-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee220-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee220-104">Syntax</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="ee220-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee220-105">Requirements</span></span>  
 <span data-ttu-id="ee220-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee220-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee220-107">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ee220-107">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ee220-108">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee220-108">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee220-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee220-109">See also</span></span>

- [<span data-ttu-id="ee220-110">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ee220-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
