---
description: '자세히 알아보기: ICorDebugValue2:: GetExactType 메서드'
title: ICorDebugValue2::GetExactType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: d0ef08b119106ced89ec2094b5bf67d0c874b6bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690308"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="1bd21-103">ICorDebugValue2::GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="1bd21-103">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="1bd21-104">이 값의을 나타내는 "ICorDebugType" 개체에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="1bd21-104">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd21-105">구문</span><span class="sxs-lookup"><span data-stu-id="1bd21-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bd21-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bd21-106">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="1bd21-107">제한이 `ICorDebugType` <xref:System.Type> 이 "ICorDebugValue2" 개체가 나타내는 값의을 나타내는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bd21-107">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bd21-108">설명</span><span class="sxs-lookup"><span data-stu-id="1bd21-108">Remarks</span></span>  

 <span data-ttu-id="1bd21-109">제네릭 인식 메서드는 `GetExactType` 각각 값의 형식에 대 한 정보를 반환 하는 [ICorDebugObjectValue:: getclass](icordebugobjectvalue-getclass-method.md) 와 [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) 메서드를 모두 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd21-109">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bd21-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bd21-110">Requirements</span></span>  

 <span data-ttu-id="1bd21-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bd21-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd21-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bd21-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bd21-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bd21-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bd21-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd21-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd21-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bd21-115">See also</span></span>
