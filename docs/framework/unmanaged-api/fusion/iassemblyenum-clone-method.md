---
title: IAssemblyEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::Clone
helpviewer_keywords:
- Clone method, IAssemblyEnum interface [.NET Framework fusion]
- IAssemblyEnum::Clone method [.NET Framework fusion]
ms.assetid: 0014bb66-590c-486c-9ade-f2133905cd99
topic_type:
- apiref
ms.openlocfilehash: e1eef43858e4f38888f9f31e3076b092fbdd5633
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719907"
---
# <a name="iassemblyenumclone-method"></a><span data-ttu-id="5c4ab-102">IAssemblyEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="5c4ab-102">IAssemblyEnum::Clone Method</span></span>

<span data-ttu-id="5c4ab-103">이 [Iassemblyenum](iassemblyenum-interface.md) 개체의 단순 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c4ab-103">Creates a shallow copy of this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c4ab-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c4ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c4ab-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5c4ab-106">제한이 복사본에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4ab-106">[out] A pointer to the copy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c4ab-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c4ab-107">Requirements</span></span>  

 <span data-ttu-id="5c4ab-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c4ab-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c4ab-109">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5c4ab-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5c4ab-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c4ab-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4ab-111">참조</span><span class="sxs-lookup"><span data-stu-id="5c4ab-111">See also</span></span>

- [<span data-ttu-id="5c4ab-112">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c4ab-112">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
