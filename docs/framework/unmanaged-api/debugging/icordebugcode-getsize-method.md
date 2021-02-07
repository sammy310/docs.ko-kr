---
description: '자세히 알아보기: ICorDebugCode:: GetSize 메서드'
title: ICorDebugCode::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
ms.openlocfilehash: 5a244d649cdcf027aea22ab36ff5d39a77a05e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711182"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="01913-103">ICorDebugCode::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="01913-103">ICorDebugCode::GetSize Method</span></span>

<span data-ttu-id="01913-104">이 "ICorDebugCode"로 표시 되는 이진 코드의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01913-104">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>

## <a name="syntax"></a><span data-ttu-id="01913-105">구문</span><span class="sxs-lookup"><span data-stu-id="01913-105">Syntax</span></span>

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a><span data-ttu-id="01913-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01913-106">Parameters</span></span>

`pcBytes`  
<span data-ttu-id="01913-107">제한이 이 개체가 나타내는 이진 코드의 크기 (바이트)에 대 한 포인터입니다 `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="01913-107">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>

## <a name="requirements"></a><span data-ttu-id="01913-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01913-108">Requirements</span></span>

<span data-ttu-id="01913-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01913-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="01913-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01913-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="01913-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01913-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="01913-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01913-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
