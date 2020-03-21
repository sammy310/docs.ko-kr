---
title: ASM_DISPLAY_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
ms.openlocfilehash: ebaab57b647250823443b48d9e45921036372d5e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176606"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="16edd-102">ASM_DISPLAY_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="16edd-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="16edd-103">[IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) 메서드에 의해 검색되는 어셈블리의 버전, 빌드, 문화권, 서명 등을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16edd-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16edd-104">구문</span><span class="sxs-lookup"><span data-stu-id="16edd-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =
                      ASM_DISPLAYF_VERSION           |
                      ASM_DISPLAYF_CULTURE           |
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |
                      ASM_DISPLAYF_RETARGET          |
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="16edd-105">설명</span><span class="sxs-lookup"><span data-stu-id="16edd-105">Remarks</span></span>  
 <span data-ttu-id="16edd-106">`ASM_DISPLAYF_FULL`는 [IAssemblyName](iassemblyname-interface.md) 개체 버전에 대한 변경 내용을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="16edd-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="16edd-107">반환된 값이 변경할 수 없다고 가정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="16edd-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16edd-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16edd-108">Requirements</span></span>  
 <span data-ttu-id="16edd-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16edd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16edd-110">**헤더:** 퓨전.h</span><span class="sxs-lookup"><span data-stu-id="16edd-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="16edd-111">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="16edd-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16edd-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16edd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16edd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16edd-113">See also</span></span>

- [<span data-ttu-id="16edd-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16edd-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="16edd-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="16edd-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
