---
description: '자세히 알아보기: ICorDebugCode:: GetEnCRemapSequencePoints 메서드'
title: ICorDebugCode::GetEnCRemapSequencePoints 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
ms.openlocfilehash: e9785460490aa602a49dff3ab972b409dde48cdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711169"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="b0447-103">ICorDebugCode::GetEnCRemapSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="b0447-103">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>

<span data-ttu-id="b0447-104">이 메서드는 현재 버전의 .NET Framework에서 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0447-104">This method is not implemented in the current version of the .NET Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0447-105">구문</span><span class="sxs-lookup"><span data-stu-id="b0447-105">Syntax</span></span>

```cpp
HRESULT GetEnCRemapSequencePoints(
    [in] ULONG32 cMap,
    [out] ULONG32 *pcMap,
    [out, size_is(cMap), length_is(*pcMap)]
        ULONG32 offsets[]
);
```
