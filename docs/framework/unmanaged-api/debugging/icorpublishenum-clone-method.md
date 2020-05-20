---
title: ICorPublishEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 38f49e8fe632e9b38ede8815de6d8865278351f9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421204"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="e16e1-102">ICorPublishEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="e16e1-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="e16e1-103">이 [ICorPublishEnum](icorpublishenum-interface.md) 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e16e1-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e16e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e16e1-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e16e1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e16e1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e16e1-106">제한이 `ICorPublishEnum`이 개체의 복사본 인 개체의 주소에 대 한 포인터입니다 `ICorPublishEnum` .</span><span class="sxs-lookup"><span data-stu-id="e16e1-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e16e1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e16e1-107">Requirements</span></span>  
 <span data-ttu-id="e16e1-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e16e1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e16e1-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e16e1-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e16e1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e16e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e16e1-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e16e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16e1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e16e1-112">See also</span></span>

- [<span data-ttu-id="e16e1-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e16e1-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
