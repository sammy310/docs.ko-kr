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
ms.openlocfilehash: b86828e01fb00b12feff2ed451793c240e16e240
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134385"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="a3611-102">IAssemblyName::GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="a3611-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="a3611-103">지정 된 속성 식별자가 참조 하는 속성에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3611-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3611-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3611-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3611-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3611-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="a3611-106">진행 요청 된 속성에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a3611-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="a3611-107">제한이 반환 된 속성 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3611-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="a3611-108">[in, out] `pvProperty`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3611-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3611-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3611-109">Requirements</span></span>  
 <span data-ttu-id="a3611-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3611-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3611-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a3611-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a3611-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3611-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3611-113">참조</span><span class="sxs-lookup"><span data-stu-id="a3611-113">See also</span></span>

- [<span data-ttu-id="a3611-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3611-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
