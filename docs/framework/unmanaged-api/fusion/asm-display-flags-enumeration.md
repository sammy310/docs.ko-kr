---
description: '다음에 대 한 자세한 정보: 열거형 ASM_DISPLAY_FLAGS'
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
ms.openlocfilehash: 82412fd4675d855f70183458bf704ac8498a6de7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761371"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="532da-103">ASM_DISPLAY_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="532da-103">ASM_DISPLAY_FLAGS Enumeration</span></span>

<span data-ttu-id="532da-104">표시 이름이 [IAssemblyName:: GetDisplayName](iassemblyname-getdisplayname-method.md) 메서드에 의해 검색 되는 어셈블리의 버전, 빌드, 문화권, 서명 등을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="532da-104">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532da-105">구문</span><span class="sxs-lookup"><span data-stu-id="532da-105">Syntax</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="532da-106">설명</span><span class="sxs-lookup"><span data-stu-id="532da-106">Remarks</span></span>  

 <span data-ttu-id="532da-107">`ASM_DISPLAYF_FULL`[IAssemblyName](iassemblyname-interface.md) 개체의 버전에 대 한 변경 내용을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="532da-107">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="532da-108">반환 된 값을 변경할 수 없는 것으로 가정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="532da-108">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532da-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="532da-109">Requirements</span></span>  

 <span data-ttu-id="532da-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="532da-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532da-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="532da-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="532da-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="532da-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="532da-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532da-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="532da-114">See also</span></span>

- [<span data-ttu-id="532da-115">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="532da-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="532da-116">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="532da-116">Fusion Enumerations</span></span>](fusion-enumerations.md)
