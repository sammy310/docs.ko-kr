---
title: SetSecurity 함수(관리되지 않는 API 참조)
description: SetSecurity 함수는 현재 스레드의 가장 토큰을 검색합니다.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176736"
---
# <a name="setsecurity-function"></a><span data-ttu-id="fce96-103">SetSecurity 함수</span><span class="sxs-lookup"><span data-stu-id="fce96-103">SetSecurity function</span></span>

<span data-ttu-id="fce96-104">현재 스레드와 연결된 가장 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fce96-105">구문</span><span class="sxs-lookup"><span data-stu-id="fce96-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="fce96-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fce96-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="fce96-107">【아웃】 함수가 반환되면 [ResetSecurity](resetsecurity.md) `boolean` 함수를 호출하여 토큰을 재설정해야 하는지 여부를 나타내는 포인터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="fce96-108">【아웃】 함수가 반환되면 현재 스레드와 연결된 가장 토큰의 핸들에 대한 포인터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="fce96-109">해당 값은 `null` 현재 스레드와 연결된 토큰이 없는 경우일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="fce96-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fce96-110">Return value</span></span>

<span data-ttu-id="fce96-111">함수가 성공하면 반환 값은 `S_OK` (0)입니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="fce96-112">함수가 실패하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="fce96-113">확장 오류 정보를 얻으려면 [GetErrorInfo](geterrorinfo.md) 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fce96-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fce96-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fce96-114">Requirements</span></span>

 <span data-ttu-id="fce96-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fce96-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="fce96-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fce96-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="fce96-117">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fce96-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fce96-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fce96-118">See also</span></span>

- [<span data-ttu-id="fce96-119">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="fce96-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
