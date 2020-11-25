---
title: ICorDebugValue::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 9f5688ae4f76f9ddfde231aa6252d666c9152eec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731083"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="b8f1c-102">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b8f1c-102">ICorDebugValue::GetSize Method</span></span>

<span data-ttu-id="b8f1c-103">이 "ICorDebugValue" 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f1c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8f1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8f1c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8f1c-105">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="b8f1c-106">제한이 이 값 개체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8f1c-107">설명</span><span class="sxs-lookup"><span data-stu-id="b8f1c-107">Remarks</span></span>  

 <span data-ttu-id="b8f1c-108">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="b8f1c-109">`ICorDebugValue::GetSize`이 메서드는 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4gb 보다 큰 개체에 대해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="b8f1c-110">4gb 보다 큰 개체에 대해 [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f1c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8f1c-111">Requirements</span></span>  

 <span data-ttu-id="b8f1c-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f1c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8f1c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8f1c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8f1c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8f1c-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f1c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f1c-116">참조</span><span class="sxs-lookup"><span data-stu-id="b8f1c-116">See also</span></span>

- [<span data-ttu-id="b8f1c-117">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="b8f1c-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
