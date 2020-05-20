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
ms.openlocfilehash: 7ed4236187fab1c1e81be9ddcdff1f1852e38f70
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421191"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="b4f6b-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="b4f6b-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="b4f6b-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4f6b-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4f6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f6b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4f6b-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="b4f6b-106">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f6b-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f6b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4f6b-107">Requirements</span></span>  
 <span data-ttu-id="b4f6b-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4f6b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f6b-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b4f6b-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b4f6b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f6b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f6b-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f6b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f6b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4f6b-112">See also</span></span>

- [<span data-ttu-id="b4f6b-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4f6b-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
