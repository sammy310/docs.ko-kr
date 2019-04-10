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
ms.openlocfilehash: a28cb9f1fd2e12cd750d4eeb8db6c2d7a181b414
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197427"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="da0b9-102">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="da0b9-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="da0b9-103">이 참조 되는 어셈블리에 대 한 버전 정보를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="da0b9-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da0b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="da0b9-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da0b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da0b9-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="da0b9-106">[out] 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="da0b9-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="da0b9-107">[out] 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="da0b9-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da0b9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da0b9-108">Requirements</span></span>  
 <span data-ttu-id="da0b9-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da0b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da0b9-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="da0b9-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="da0b9-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="da0b9-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da0b9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="da0b9-112">See also</span></span>

- [<span data-ttu-id="da0b9-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da0b9-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
