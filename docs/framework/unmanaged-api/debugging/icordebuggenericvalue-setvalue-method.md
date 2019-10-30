---
title: ICorDebugGenericValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
ms.openlocfilehash: 4cd03895b4e33c3e42c71acca12eaf950fc9a145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138553"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="3cc73-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="3cc73-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="3cc73-103">지정 된 버퍼에서 새 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc73-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc73-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cc73-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cc73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cc73-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="3cc73-106">진행 값을 복사할 원본 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3cc73-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cc73-107">주의</span><span class="sxs-lookup"><span data-stu-id="3cc73-107">Remarks</span></span>  
 <span data-ttu-id="3cc73-108">참조 형식의 경우 값은 콘텐츠가 아닌 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="3cc73-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc73-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3cc73-109">Requirements</span></span>  
 <span data-ttu-id="3cc73-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cc73-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc73-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cc73-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cc73-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cc73-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cc73-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc73-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
