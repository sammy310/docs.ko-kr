---
description: '다음에 대 한 자세한 정보: ICorDebugValue:: GetAddress 메서드'
title: ICorDebugValue::GetAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: c922388fbab820e50edffc140be94a2c0920099d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690433"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="12571-103">ICorDebugValue::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="12571-103">ICorDebugValue::GetAddress Method</span></span>

<span data-ttu-id="12571-104">디버깅 중인이 "ICorDebugValue" 개체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12571-104">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12571-105">구문</span><span class="sxs-lookup"><span data-stu-id="12571-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12571-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12571-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="12571-107">제한이 `CORDB_ADDRESS` 이 값 개체의 주소를 지정 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12571-107">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12571-108">설명</span><span class="sxs-lookup"><span data-stu-id="12571-108">Remarks</span></span>  

 <span data-ttu-id="12571-109">값을 사용할 수 없는 경우 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12571-109">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="12571-110">이는 값이 최소한 레지스터에 있거나 가비지 수집기 핸들 ()에 저장 된 경우에 발생할 수 있습니다 `GCHandle` .</span><span class="sxs-lookup"><span data-stu-id="12571-110">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12571-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12571-111">Requirements</span></span>  

 <span data-ttu-id="12571-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12571-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12571-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12571-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12571-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12571-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12571-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12571-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12571-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12571-116">See also</span></span>
