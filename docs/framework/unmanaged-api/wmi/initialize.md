---
title: Initialize 함수 (관리 되지 않는 API 참조)
description: Initialize 함수는 WMI 초기화를 수행 합니다.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127387"
---
# <a name="initialize-function"></a><span data-ttu-id="39132-103">Initialize 함수</span><span class="sxs-lookup"><span data-stu-id="39132-103">Initialize function</span></span>

<span data-ttu-id="39132-104">WMI 초기화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="39132-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="39132-105">구문</span><span class="sxs-lookup"><span data-stu-id="39132-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="39132-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39132-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="39132-107">[in] WMI 개체에 대 한 QueryInterface 호출이 허용 됨을 나타내는 `true`입니다. 그렇지 않으면 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39132-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="39132-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="39132-108">Return value</span></span>

<span data-ttu-id="39132-109">함수는 항상 `S_OK` (0)를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39132-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="39132-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39132-110">Requirements</span></span>

<span data-ttu-id="39132-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39132-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="39132-112">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="39132-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="39132-113">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39132-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="39132-114">참조</span><span class="sxs-lookup"><span data-stu-id="39132-114">See also</span></span>

- [<span data-ttu-id="39132-115">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="39132-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
