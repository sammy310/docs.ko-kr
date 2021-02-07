---
description: '다음에 대 한 자세한 정보: IAssemblyEnum:: Clone 메서드'
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
ms.openlocfilehash: 0b4da5818b66d5b82da0b693c2d1cfa257f08a7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760838"
---
# <a name="iassemblyenumclone-method"></a><span data-ttu-id="b509b-103">IAssemblyEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="b509b-103">IAssemblyEnum::Clone Method</span></span>

<span data-ttu-id="b509b-104">이 [Iassemblyenum](iassemblyenum-interface.md) 개체의 단순 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b509b-104">Creates a shallow copy of this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b509b-105">구문</span><span class="sxs-lookup"><span data-stu-id="b509b-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b509b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b509b-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="b509b-107">제한이 복사본에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b509b-107">[out] A pointer to the copy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b509b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b509b-108">Requirements</span></span>  

 <span data-ttu-id="b509b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b509b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b509b-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b509b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b509b-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b509b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b509b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b509b-112">See also</span></span>

- [<span data-ttu-id="b509b-113">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b509b-113">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
