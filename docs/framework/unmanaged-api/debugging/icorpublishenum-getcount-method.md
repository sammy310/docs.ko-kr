---
title: ICorPublishEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a23d61da2913d8732c3860a44eb58ffadab48315
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677936"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="d2c16-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d2c16-102">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="d2c16-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2c16-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c16-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2c16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c16-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2c16-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="d2c16-106">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c16-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c16-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2c16-107">Requirements</span></span>  

 <span data-ttu-id="d2c16-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c16-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c16-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="d2c16-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d2c16-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2c16-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2c16-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c16-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c16-112">참조</span><span class="sxs-lookup"><span data-stu-id="d2c16-112">See also</span></span>

- [<span data-ttu-id="d2c16-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2c16-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
