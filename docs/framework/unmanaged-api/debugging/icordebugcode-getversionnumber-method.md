---
title: ICorDebugCode::GetVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
ms.openlocfilehash: 646c20ca1b78ff0ce513b8a3c9b578c3b1b9a696
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125608"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="341d5-102">ICorDebugCode::GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="341d5-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="341d5-103">이 "ICorDebugCode"가 나타내는 코드의 버전을 식별 하는 1부터 사용 하는 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="341d5-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="341d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="341d5-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="341d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="341d5-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="341d5-106">제한이 코드의 버전 번호에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="341d5-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="341d5-107">주의</span><span class="sxs-lookup"><span data-stu-id="341d5-107">Remarks</span></span>

 <span data-ttu-id="341d5-108">코드에서 편집 하며 계속 하기 (EnC) 작업이 수행 될 때마다 버전 번호가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="341d5-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="341d5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="341d5-109">Requirements</span></span>

 <span data-ttu-id="341d5-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="341d5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="341d5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="341d5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="341d5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="341d5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="341d5-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="341d5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
