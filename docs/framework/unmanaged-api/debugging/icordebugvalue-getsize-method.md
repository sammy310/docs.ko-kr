---
description: '다음에 대 한 자세한 정보: ICorDebugValue:: GetSize 메서드'
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
ms.openlocfilehash: 3fc2582990d58fa2e42f240dfd3e563eed34e372
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690342"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="13fa0-103">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="13fa0-103">ICorDebugValue::GetSize Method</span></span>

<span data-ttu-id="13fa0-104">이 "ICorDebugValue" 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fa0-104">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fa0-105">구문</span><span class="sxs-lookup"><span data-stu-id="13fa0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13fa0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13fa0-106">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="13fa0-107">제한이 이 값 개체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="13fa0-107">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13fa0-108">설명</span><span class="sxs-lookup"><span data-stu-id="13fa0-108">Remarks</span></span>  

 <span data-ttu-id="13fa0-109">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fa0-109">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="13fa0-110">`ICorDebugValue::GetSize`이 메서드는 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4gb 보다 큰 개체에 대해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fa0-110">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="13fa0-111">4gb 보다 큰 개체에 대해 [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fa0-111">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fa0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13fa0-112">Requirements</span></span>  

 <span data-ttu-id="13fa0-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13fa0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fa0-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13fa0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13fa0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13fa0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13fa0-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fa0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fa0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13fa0-117">See also</span></span>

- [<span data-ttu-id="13fa0-118">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="13fa0-118">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
