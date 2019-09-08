---
title: ASM_NAME 열거형
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 698fb8c8efcbe347c0e833b0dba01fffd3030de6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795502"
---
# <a name="asm_name-enumeration"></a><span data-ttu-id="427f8-102">ASM_NAME 열거형</span><span class="sxs-lookup"><span data-stu-id="427f8-102">ASM_NAME Enumeration</span></span>
<span data-ttu-id="427f8-103">[IAssemblyName](iassemblyname-interface.md) 메서드에서 속성을 검색 하거나 설정 하는 어셈블리의 버전, 빌드, 문화권, 서명 등을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="427f8-103">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](iassemblyname-interface.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="427f8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,   
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a><span data-ttu-id="427f8-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="427f8-105">Requirements</span></span>  
 <span data-ttu-id="427f8-106">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="427f8-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427f8-107">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="427f8-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="427f8-108">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="427f8-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="427f8-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427f8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427f8-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="427f8-110">See also</span></span>

- [<span data-ttu-id="427f8-111">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="427f8-111">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="427f8-112">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="427f8-112">Fusion Enumerations</span></span>](fusion-enumerations.md)
