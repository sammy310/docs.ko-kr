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
ms.openlocfilehash: af9ca932a4c4a12a2c89571f40162a4ecbd5c33d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144497"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="33bb0-102">CorArgType 열거형</span><span class="sxs-lookup"><span data-stu-id="33bb0-102">CorArgType Enumeration</span></span>
<span data-ttu-id="33bb0-103">런타임 핸들의 네이티브 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33bb0-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="33bb0-104">Syntax</span></span>  
  
```  
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
  
## <a name="requirements"></a><span data-ttu-id="33bb0-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33bb0-105">Requirements</span></span>  
 <span data-ttu-id="33bb0-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33bb0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33bb0-107">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="33bb0-107">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="33bb0-108">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="33bb0-108">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33bb0-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="33bb0-109">See also</span></span>

- [<span data-ttu-id="33bb0-110">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="33bb0-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
