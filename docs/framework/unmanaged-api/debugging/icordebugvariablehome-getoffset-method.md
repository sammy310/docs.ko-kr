---
title: 'ICorDebugVariableHome:: GetOffset 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711795"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="8204f-102">ICorDebugVariableHome:: GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="8204f-102">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="8204f-103">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8204f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8204f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8204f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8204f-105">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="8204f-106">제한이 기본 레지스터의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8204f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8204f-107">Return Value</span></span>  

 <span data-ttu-id="8204f-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="8204f-109">값</span><span class="sxs-lookup"><span data-stu-id="8204f-109">Value</span></span>|<span data-ttu-id="8204f-110">설명</span><span class="sxs-lookup"><span data-stu-id="8204f-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="8204f-111">변수가 등록 관련 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="8204f-112">변수가 등록 관련 메모리 위치에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8204f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8204f-113">Requirements</span></span>  

 <span data-ttu-id="8204f-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8204f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8204f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8204f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8204f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8204f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8204f-117">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8204f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8204f-118">참조</span><span class="sxs-lookup"><span data-stu-id="8204f-118">See also</span></span>

- [<span data-ttu-id="8204f-119">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8204f-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
