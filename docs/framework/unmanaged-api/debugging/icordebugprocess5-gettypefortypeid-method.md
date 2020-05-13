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
ms.openlocfilehash: ea7f7a9d4589e4f08b1b1e20b4d073bb5f822714
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212765"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="c4db9-102">ICorDebugProcess5::GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="c4db9-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="c4db9-103">형식 식별자를 ICorDebugType 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4db9-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4db9-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4db9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4db9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4db9-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c4db9-106">진행 유형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c4db9-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c4db9-107">제한이 ICorDebugType 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4db9-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4db9-108">설명</span><span class="sxs-lookup"><span data-stu-id="c4db9-108">Remarks</span></span>  
 <span data-ttu-id="c4db9-109">경우에 따라 형식 식별자를 반환 하는 메서드는 null 값을 반환할 수 있습니다 `COR_TYPEID` .</span><span class="sxs-lookup"><span data-stu-id="c4db9-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="c4db9-110">이 값이 인수로 전달 되 면 `id` `GetTypeForTypeID` 메서드가 실패 하 고이 반환 됩니다 `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="c4db9-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4db9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4db9-111">Requirements</span></span>  
 <span data-ttu-id="c4db9-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4db9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4db9-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4db9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4db9-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4db9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4db9-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4db9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4db9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4db9-116">See also</span></span>

- [<span data-ttu-id="c4db9-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4db9-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="c4db9-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4db9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
