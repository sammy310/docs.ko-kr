---
title: ICorDebugCode::IsIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b7cbadbd1494d5e4d1488dd12296f4f90890127
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395493"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="7e3d6-102">ICorDebugCode::IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="7e3d6-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="7e3d6-103">이 "ICorDebugCode"가 MSIL (Microsoft 중간 언어)로 컴파일된 코드를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e3d6-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="7e3d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e3d6-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="7e3d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e3d6-105">Parameters</span></span>

`pbIL`  
<span data-ttu-id="7e3d6-106">[out] `ICorDebugCode` @no__t MSIL로 컴파일된 코드를 나타내는 경우 0입니다. 그렇지 않으면-2를 @no__t 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3d6-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e3d6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e3d6-107">Requirements</span></span>

<span data-ttu-id="7e3d6-108">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e3d6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7e3d6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e3d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="7e3d6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e3d6-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7e3d6-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e3d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
