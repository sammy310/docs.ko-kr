---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25349f7c8274b818df2cd1bc5d67856e31efecc4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395541"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="f3916-102">ICorDebugCode::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="f3916-102">ICorDebugCode::GetSize Method</span></span>

<span data-ttu-id="f3916-103">이 "ICorDebugCode"로 표시 되는 이진 코드의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3916-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>

## <a name="syntax"></a><span data-ttu-id="f3916-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3916-104">Syntax</span></span>

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a><span data-ttu-id="f3916-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3916-105">Parameters</span></span>

`pcBytes`  
<span data-ttu-id="f3916-106">제한이 이 `ICorDebugCode` 개체가 나타내는 이진 코드의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3916-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3916-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3916-107">Requirements</span></span>

<span data-ttu-id="f3916-108">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3916-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f3916-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3916-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="f3916-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3916-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f3916-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3916-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
