---
title: ICorDebugProcess5::GetTypeForTypeID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4ad1dffe4553b243b5168037aea8b68f8244b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930210"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="8d02f-102">ICorDebugProcess5::GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="8d02f-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="8d02f-103">형식 식별자를 ICorDebugType 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d02f-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d02f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d02f-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d02f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d02f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="8d02f-106">[in] 형식 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d02f-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="8d02f-107">[out] ICorDebugType 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8d02f-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d02f-108">설명</span><span class="sxs-lookup"><span data-stu-id="8d02f-108">Remarks</span></span>  
 <span data-ttu-id="8d02f-109">경우에 따라 형식 식별자를 반환 하는 메서드는 null을 반환 `COR_TYPEID` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d02f-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="8d02f-110">이 값으로 전달 될 합니다 `id` 인수를 `GetTypeForTypeID` 메서드는 실패 하 고 반환 `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="8d02f-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d02f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d02f-111">Requirements</span></span>  
 <span data-ttu-id="8d02f-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d02f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d02f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d02f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d02f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d02f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d02f-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d02f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d02f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d02f-116">See also</span></span>

- [<span data-ttu-id="8d02f-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d02f-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="8d02f-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d02f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
