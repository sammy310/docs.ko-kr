---
title: IAssemblyName::GetProperty 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9af0773c2ef066c103f823e4d28c0fd6e9eadc24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086561"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="10bd1-102">IAssemblyName::GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="10bd1-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="10bd1-103">지정 된 속성 식별자가 참조 하는 속성에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10bd1-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10bd1-104">구문</span><span class="sxs-lookup"><span data-stu-id="10bd1-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10bd1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10bd1-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="10bd1-106">[in] 요청된 된 속성에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="10bd1-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="10bd1-107">[out] 반환 된 속성을 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="10bd1-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="10bd1-108">[out에서] 크기 (바이트)의 `pvProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="10bd1-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10bd1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10bd1-109">Requirements</span></span>  
 <span data-ttu-id="10bd1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10bd1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10bd1-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="10bd1-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="10bd1-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10bd1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10bd1-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="10bd1-113">See also</span></span>

- [<span data-ttu-id="10bd1-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10bd1-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
