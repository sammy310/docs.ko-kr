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
ms.openlocfilehash: 0b3754fbcca50b52039dc358aed7070b8a152ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790630"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="ca3df-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="ca3df-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="ca3df-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca3df-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca3df-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca3df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca3df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca3df-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="ca3df-106">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3df-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca3df-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca3df-107">Requirements</span></span>  
 <span data-ttu-id="ca3df-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3df-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca3df-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ca3df-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ca3df-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca3df-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca3df-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca3df-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3df-112">참조</span><span class="sxs-lookup"><span data-stu-id="ca3df-112">See also</span></span>

- [<span data-ttu-id="ca3df-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca3df-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
