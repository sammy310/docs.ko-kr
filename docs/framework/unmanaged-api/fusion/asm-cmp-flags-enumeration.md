---
title: ASM_CMP_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- ASM_CMP_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CMP_FLAGS
helpviewer_keywords:
- ASM_CMP_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 4d1e6700-d4be-4fbd-8796-bfb4c07abbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28157d2ed223d89af4b4314035e7c03d572be7b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778559"
---
# <a name="asmcmpflags-enumeration"></a><span data-ttu-id="0db6a-102">ASM_CMP_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="0db6a-102">ASM_CMP_FLAGS Enumeration</span></span>
<span data-ttu-id="0db6a-103">버전, 빌드, 문화권, 서명 및 등과에서 비교할 두 명의 어셈블리를 나타내는 합니다 [iassemblyname:: Isequal](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0db6a-103">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0db6a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_CMPF_NAME                   = 0x1,  
    ASM_CMPF_MAJOR_VERSION          = 0x2,  
    ASM_CMPF_MINOR_VERSION          = 0x4,  
    ASM_CMPF_BUILD_NUMBER           = 0x8,  
    ASM_CMPF_REVISION_NUMBER        = 0x10,  
  
    ASM_CMPF_VERSION                =   
                 ASM_CMPF_MAJOR_VERSION |   
                 ASM_CMPF_MINOR_VERSION |   
                 ASM_CMPF_BUILD_NUMBER  |   
                 ASM_CMPF_REVISION_NUMBER,  
  
    ASM_CMPF_PUBLIC_KEY_TOKEN       = 0x20,  
    ASM_CMPF_CULTURE                = 0x40,  
    ASM_CMPF_CUSTOM                 = 0x80,  
    ASM_CMPF_DEFAULT                = 0x100,  
    ASM_CMPF_RETARGET               = 0x200,  
    ASM_CMPF_ARCHITECTURE           = 0x400,  
    ASM_CMPF_CONFIG_MASK            = 0x800,  
    ASM_CMPF_MVID                   = 0x1000,  
    ASM_CMPF_SIGNATURE              = 0x2000,  
  
    ASM_CMPF_IL_ALL                 =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_VERSION          |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE,  
  
    ASM_CMPF_IL_NO_VERSION          =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE  
  
} ASM_CMP_FLAGS;  
```  
  
## <a name="requirements"></a><span data-ttu-id="0db6a-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0db6a-105">Requirements</span></span>  
 <span data-ttu-id="0db6a-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0db6a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0db6a-107">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0db6a-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0db6a-108">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0db6a-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0db6a-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0db6a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db6a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="0db6a-110">See also</span></span>

- [<span data-ttu-id="0db6a-111">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0db6a-111">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="0db6a-112">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="0db6a-112">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
