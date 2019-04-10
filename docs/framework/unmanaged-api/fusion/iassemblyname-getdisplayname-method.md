---
title: IAssemblyName::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 323c883b4010f3ddd4c575e5d5fc40a3419e57c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214366"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="bbd37-102">IAssemblyName::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="bbd37-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="bbd37-103">이 참조 되는 어셈블리의 알기 쉬운 이름을 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd37-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd37-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbd37-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbd37-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbd37-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="bbd37-106">[out] 참조 된 어셈블리의 이름이 들어 있는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd37-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="bbd37-107">[out에서] 크기 `szDisplayName` 와이드 문자에서 null 종결 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd37-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="bbd37-108">[in] 비트 조합 [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) 의 기능에 영향을 주는 값 `szDisplayName`합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd37-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd37-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbd37-109">Requirements</span></span>  
 <span data-ttu-id="bbd37-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbd37-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd37-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bbd37-111">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="bbd37-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="bbd37-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbd37-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbd37-113">See also</span></span>

- [<span data-ttu-id="bbd37-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbd37-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="bbd37-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="bbd37-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
