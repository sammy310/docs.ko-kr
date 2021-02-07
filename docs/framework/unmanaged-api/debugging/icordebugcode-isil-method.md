---
description: '자세히 알아보기: ICorDebugCode:: IsIL 메서드'
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
ms.openlocfilehash: db41f9ebaa6a6403b21e10d1daa0e8b167c7cb96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711128"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="b4f5c-103">ICorDebugCode::IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="b4f5c-103">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="b4f5c-104">이 "ICorDebugCode"가 MSIL (Microsoft 중간 언어)로 컴파일된 코드를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4f5c-104">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="b4f5c-105">구문</span><span class="sxs-lookup"><span data-stu-id="b4f5c-105">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="b4f5c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4f5c-106">Parameters</span></span>

`pbIL`  
<span data-ttu-id="b4f5c-107">[out] `true` 이가 `ICorDebugCode` MSIL로 컴파일된 코드를 나타내면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f5c-107">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4f5c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4f5c-108">Requirements</span></span>

<span data-ttu-id="b4f5c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4f5c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b4f5c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4f5c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b4f5c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f5c-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b4f5c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f5c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
