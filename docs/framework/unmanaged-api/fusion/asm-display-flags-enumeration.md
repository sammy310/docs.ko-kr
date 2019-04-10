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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcff46b1932f3293fba4fda922e78f3b9ac37b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148852"
---
# <a name="asmdisplayflags-enumeration"></a><span data-ttu-id="ad18d-102">ASM_DISPLAY_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="ad18d-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="ad18d-103">버전, 빌드, 문화권, 서명 및 등에 의해 검색 됩니다 표시 이름이 어셈블리의 나타냅니다 합니다 [iassemblyname:: Getdisplayname](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ad18d-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad18d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad18d-104">Syntax</span></span>  
  
```  
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
  
## <a name="remarks"></a><span data-ttu-id="ad18d-105">설명</span><span class="sxs-lookup"><span data-stu-id="ad18d-105">Remarks</span></span>  
 `ASM_DISPLAYF_FULL` <span data-ttu-id="ad18d-106">버전에 대 한 모든 변경 내용을 반영 합니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ad18d-106">reflects any changes made to the version of the [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span> <span data-ttu-id="ad18d-107">반환 된 값을 변경할 수 없는 가정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ad18d-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad18d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad18d-108">Requirements</span></span>  
 <span data-ttu-id="ad18d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad18d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad18d-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ad18d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ad18d-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ad18d-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ad18d-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ad18d-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad18d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad18d-113">See also</span></span>

- [<span data-ttu-id="ad18d-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad18d-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="ad18d-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="ad18d-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
