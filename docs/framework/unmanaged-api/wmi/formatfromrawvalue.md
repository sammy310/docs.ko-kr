---
title: FormatFromRawValue 함수(관리되지 않는 API 참조)
description: FormatFromRawValue 함수는 원시 성능 데이터를 지정된 형식으로 변환합니다.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176840"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="aa7d7-103">FormatFromRawValue 함수</span><span class="sxs-lookup"><span data-stu-id="aa7d7-103">FormatFromRawValue function</span></span>
<span data-ttu-id="aa7d7-104">형식 변환이 시간 기반인 경우 하나의 원시 성능 데이터 값을 지정된 형식으로 변화하거나 두 개의 원시 성능 데이터 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="aa7d7-105">구문</span><span class="sxs-lookup"><span data-stu-id="aa7d7-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType,
   [in] uint                    dwFormat,
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
);
```

## <a name="parameters"></a><span data-ttu-id="aa7d7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa7d7-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="aa7d7-107">【인】 카운터 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-107">[in] The counter type.</span></span> <span data-ttu-id="aa7d7-108">카운터 유형 목록은 [WMI 성능 카운터 유형을](/windows/desktop/WmiSdk/wmi-performance-counter-types)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="aa7d7-109">`dwCounterType`카운터 유형이 `PERF_LARGE_RAW_FRACTION` 될 수 `PERF_LARGE_RAW_BASE`있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="aa7d7-110">【인】 원시 성능 데이터를 변환할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="aa7d7-111">다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-111">It can be one of the following values:</span></span>

|<span data-ttu-id="aa7d7-112">지속적임</span><span class="sxs-lookup"><span data-stu-id="aa7d7-112">Constant</span></span>  |<span data-ttu-id="aa7d7-113">값</span><span class="sxs-lookup"><span data-stu-id="aa7d7-113">Value</span></span>  |<span data-ttu-id="aa7d7-114">Description</span><span class="sxs-lookup"><span data-stu-id="aa7d7-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="aa7d7-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="aa7d7-115">0x00000200</span></span> | <span data-ttu-id="aa7d7-116">계산된 값을 이중 정밀도 부동 점 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="aa7d7-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="aa7d7-117">0x00000400</span></span> | <span data-ttu-id="aa7d7-118">계산된 값을 64비트 정수로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="aa7d7-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="aa7d7-119">0x00000100</span></span> | <span data-ttu-id="aa7d7-120">계산된 값을 32비트 정수로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="aa7d7-121">이전 값 중 하나는 다음 크기 조정 플래그 중 하나를 사용할 수 있는 ORed일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="aa7d7-122">지속적임</span><span class="sxs-lookup"><span data-stu-id="aa7d7-122">Constant</span></span>  |<span data-ttu-id="aa7d7-123">값</span><span class="sxs-lookup"><span data-stu-id="aa7d7-123">Value</span></span>  |<span data-ttu-id="aa7d7-124">Description</span><span class="sxs-lookup"><span data-stu-id="aa7d7-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="aa7d7-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="aa7d7-125">0x00001000</span></span> | <span data-ttu-id="aa7d7-126">카운터의 배율 계수 요소를 적용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="aa7d7-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="aa7d7-127">0x00002000</span></span> | <span data-ttu-id="aa7d7-128">최종 값에 1,000을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="aa7d7-129">【인】 형식 변환에 필요한 경우 시간 기반에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="aa7d7-130">형식 변환에 시간 기준 정보가 필요하지 않은 경우 이 매개 변수의 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="aa7d7-131">【인】 원시 성능 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 값을 나타내는 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="aa7d7-132">【인】 두 번째 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 원시 성능 값을 나타내는 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="aa7d7-133">두 번째 원시 성능 값이 필요하지 않은 `null`경우 이 매개 변수는 이 매개 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="aa7d7-134">【아웃】 형식이 [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) 지정된 성능 값을 받는 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa7d7-135">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa7d7-135">Return value</span></span>

<span data-ttu-id="aa7d7-136">다음 값은 이 함수에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="aa7d7-137">지속적임</span><span class="sxs-lookup"><span data-stu-id="aa7d7-137">Constant</span></span>  |<span data-ttu-id="aa7d7-138">값</span><span class="sxs-lookup"><span data-stu-id="aa7d7-138">Value</span></span>  |<span data-ttu-id="aa7d7-139">Description</span><span class="sxs-lookup"><span data-stu-id="aa7d7-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="aa7d7-140">0</span><span class="sxs-lookup"><span data-stu-id="aa7d7-140">0</span></span> | <span data-ttu-id="aa7d7-141">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="aa7d7-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="aa7d7-142">0xC0000BBD</span></span> | <span data-ttu-id="aa7d7-143">필요한 인수가 없거나 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="aa7d7-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="aa7d7-144">0xC0000BBC</span></span> | <span data-ttu-id="aa7d7-145">핸들이 유효한 PDH 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="aa7d7-146">설명</span><span class="sxs-lookup"><span data-stu-id="aa7d7-146">Remarks</span></span>

<span data-ttu-id="aa7d7-147">이 함수는 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) 함수에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa7d7-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa7d7-148">Requirements</span></span>

 <span data-ttu-id="aa7d7-149">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa7d7-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="aa7d7-150">**라이브러리:** 퍼프카운터.dll</span><span class="sxs-lookup"><span data-stu-id="aa7d7-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="aa7d7-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa7d7-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aa7d7-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa7d7-152">See also</span></span>

- [<span data-ttu-id="aa7d7-153">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="aa7d7-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
