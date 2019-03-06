---
title: IAssemblyName::GetVersion 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7479e8d1eee0c44544b5923d4de66153cb2c3a19
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490335"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="a7ba9-102">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="a7ba9-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="a7ba9-103">이 참조 되는 어셈블리에 대 한 버전 정보를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba9-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ba9-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7ba9-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ba9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7ba9-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="a7ba9-106">[out] 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba9-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="a7ba9-107">[out] 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba9-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ba9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7ba9-108">Requirements</span></span>  
 <span data-ttu-id="a7ba9-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7ba9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ba9-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a7ba9-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a7ba9-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ba9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ba9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7ba9-112">See also</span></span>
- [<span data-ttu-id="a7ba9-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7ba9-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
