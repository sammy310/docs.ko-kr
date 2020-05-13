---
title: ICorDebugProcess5::GetTypeID 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 499e1fd859a66bb6992c6d02a46e38c514503bd8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205593"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="371a0-102">ICorDebugProcess5::GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="371a0-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="371a0-103">개체 주소를 [COR_TYPEID](cor-typeid-structure.md) 식별자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="371a0-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="371a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="371a0-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="371a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="371a0-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="371a0-106">진행 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="371a0-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="371a0-107">개체를 식별 하는 [COR_TYPEID](cor-typeid-structure.md) 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="371a0-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="371a0-108">설명</span><span class="sxs-lookup"><span data-stu-id="371a0-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="371a0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="371a0-109">Requirements</span></span>  
 <span data-ttu-id="371a0-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="371a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="371a0-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="371a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="371a0-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="371a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="371a0-113">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="371a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371a0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="371a0-114">See also</span></span>

- [<span data-ttu-id="371a0-115">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371a0-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="371a0-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371a0-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
