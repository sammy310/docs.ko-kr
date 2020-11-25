---
title: 'ICorDebugVariableHome:: GetSlotIndex 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 4b071bd8e9d96084848c1553385eec5f8beca624
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711730"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="bba53-102">ICorDebugVariableHome:: GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="bba53-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>

<span data-ttu-id="bba53-103">지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bba53-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba53-104">구문</span><span class="sxs-lookup"><span data-stu-id="bba53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bba53-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bba53-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="bba53-106">제한이 지역 변수의 슬롯 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bba53-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bba53-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="bba53-107">Return Value</span></span>  

 <span data-ttu-id="bba53-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba53-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="bba53-109">값</span><span class="sxs-lookup"><span data-stu-id="bba53-109">Value</span></span>|<span data-ttu-id="bba53-110">설명</span><span class="sxs-lookup"><span data-stu-id="bba53-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="bba53-111">메서드 호출이에서 슬롯 인덱스 값을 반환 했습니다 `pSlotIndex` .</span><span class="sxs-lookup"><span data-stu-id="bba53-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="bba53-112">현재 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스는 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bba53-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bba53-113">설명</span><span class="sxs-lookup"><span data-stu-id="bba53-113">Remarks</span></span>  

 <span data-ttu-id="bba53-114">슬롯 인덱스를 사용 하 여이 지역 변수에 대 한 메타 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba53-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bba53-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bba53-115">Requirements</span></span>  

 <span data-ttu-id="bba53-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bba53-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bba53-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bba53-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bba53-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bba53-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bba53-119">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bba53-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba53-120">참조</span><span class="sxs-lookup"><span data-stu-id="bba53-120">See also</span></span>

- [<span data-ttu-id="bba53-121">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bba53-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
