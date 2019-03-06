---
title: IAssemblyName::Clone 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a6d0036a1f4c499505743fd15a115f870e9cb50
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492402"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="0a0be-102">IAssemblyName::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="0a0be-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="0a0be-103">이 항목의 단순 복사본을 만듭니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0be-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0be-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a0be-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a0be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a0be-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="0a0be-106">[out] 이 반환 되는 복사본 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0be-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0be-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a0be-107">Requirements</span></span>  
 <span data-ttu-id="0a0be-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a0be-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0be-109">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0a0be-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0a0be-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0be-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0be-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a0be-111">See also</span></span>
- [<span data-ttu-id="0a0be-112">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a0be-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
