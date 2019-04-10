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
ms.openlocfilehash: 2c824874d340aa3d381b3340408021ef1ed7eec6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166701"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="864c8-102">IAssemblyName::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="864c8-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="864c8-103">이 항목의 단순 복사본을 만듭니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="864c8-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="864c8-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="864c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="864c8-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="864c8-106">[out] 이 반환 되는 복사본 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="864c8-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="864c8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="864c8-107">Requirements</span></span>  
 <span data-ttu-id="864c8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="864c8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864c8-109">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="864c8-109">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="864c8-110">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="864c8-110">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="864c8-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="864c8-111">See also</span></span>

- [<span data-ttu-id="864c8-112">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="864c8-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
