---
title: FormatFromRawValue 함수 (관리 되지 않는 API 참조)
description: FormatFromRawValue 함수는 원시 성능 데이터를 지정 된 형식으로 변환 합니다.
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
ms.openlocfilehash: 5097cfe43ae785461a1e2af1217bcbd5e8c4b79c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120281"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="988f2-103">FormatFromRawValue 함수</span><span class="sxs-lookup"><span data-stu-id="988f2-103">FormatFromRawValue function</span></span>
<span data-ttu-id="988f2-104">형식 변환이 시간 기반인 경우 하나의 원시 성능 데이터 값을 지정된 형식으로 변화하거나 두 개의 원시 성능 데이터 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="988f2-105">구문</span><span class="sxs-lookup"><span data-stu-id="988f2-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="988f2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="988f2-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="988f2-107">진행 카운터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-107">[in] The counter type.</span></span> <span data-ttu-id="988f2-108">카운터 형식 목록은 [WMI 성능 카운터 형식](/windows/desktop/WmiSdk/wmi-performance-counter-types)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="988f2-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="988f2-109">`dwCounterType`은 `PERF_LARGE_RAW_FRACTION` 및 `PERF_LARGE_RAW_BASE`를 제외한 모든 카운터 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="988f2-110">진행 원시 성능 데이터를 변환할 대상 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="988f2-111">다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-111">It can be one of the following values:</span></span>

|<span data-ttu-id="988f2-112">상수</span><span class="sxs-lookup"><span data-stu-id="988f2-112">Constant</span></span>  |<span data-ttu-id="988f2-113">값</span><span class="sxs-lookup"><span data-stu-id="988f2-113">Value</span></span>  |<span data-ttu-id="988f2-114">설명</span><span class="sxs-lookup"><span data-stu-id="988f2-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="988f2-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="988f2-115">0x00000200</span></span> | <span data-ttu-id="988f2-116">계산 된 값을 배정밀도 부동 소수점 값으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="988f2-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="988f2-117">0x00000400</span></span> | <span data-ttu-id="988f2-118">계산 된 값을 64 비트 정수로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="988f2-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="988f2-119">0x00000100</span></span> | <span data-ttu-id="988f2-120">계산 된 값을 32 비트 정수로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="988f2-121">이전 값 중 하나는 다음 크기 조정 플래그 중 하나를 사용 하 여 ORed 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="988f2-122">상수</span><span class="sxs-lookup"><span data-stu-id="988f2-122">Constant</span></span>  |<span data-ttu-id="988f2-123">값</span><span class="sxs-lookup"><span data-stu-id="988f2-123">Value</span></span>  |<span data-ttu-id="988f2-124">설명</span><span class="sxs-lookup"><span data-stu-id="988f2-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="988f2-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="988f2-125">0x00001000</span></span> | <span data-ttu-id="988f2-126">카운터의 배율 인수를 적용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="988f2-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="988f2-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="988f2-127">0x00002000</span></span> | <span data-ttu-id="988f2-128">최종 값을 1000에 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="988f2-129">진행 형식 변환에 필요한 경우 시간 기준에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="988f2-130">형식 변환에 시간 기준 정보가 필요 하지 않은 경우이 매개 변수 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="988f2-131">`pRawValue1`\ [in] 원시 성능 값을 나타내는 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="988f2-132">진행 두 번째 원시 성능 값을 나타내는 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="988f2-133">두 번째 원시 성능 값이 필요 하지 않은 경우이 매개 변수를 `null`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="988f2-134">제한이 형식이 지정 된 성능 값을 받는 [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="988f2-135">반환 값</span><span class="sxs-lookup"><span data-stu-id="988f2-135">Return value</span></span>

<span data-ttu-id="988f2-136">이 함수에서 반환 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="988f2-137">상수</span><span class="sxs-lookup"><span data-stu-id="988f2-137">Constant</span></span>  |<span data-ttu-id="988f2-138">값</span><span class="sxs-lookup"><span data-stu-id="988f2-138">Value</span></span>  |<span data-ttu-id="988f2-139">설명</span><span class="sxs-lookup"><span data-stu-id="988f2-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="988f2-140">0</span><span class="sxs-lookup"><span data-stu-id="988f2-140">0</span></span> | <span data-ttu-id="988f2-141">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="988f2-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="988f2-142">0xC0000BBD</span></span> | <span data-ttu-id="988f2-143">필요한 인수가 없거나 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="988f2-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="988f2-144">0xC0000BBC</span></span> | <span data-ttu-id="988f2-145">핸들이 올바른 PDH 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="988f2-146">주의</span><span class="sxs-lookup"><span data-stu-id="988f2-146">Remarks</span></span>

<span data-ttu-id="988f2-147">이 함수는 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) 함수에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="988f2-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="988f2-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="988f2-148">Requirements</span></span>

 <span data-ttu-id="988f2-149">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="988f2-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="988f2-150">**라이브러리:** PerfCounter</span><span class="sxs-lookup"><span data-stu-id="988f2-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="988f2-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="988f2-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="988f2-152">참조</span><span class="sxs-lookup"><span data-stu-id="988f2-152">See also</span></span>

- [<span data-ttu-id="988f2-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="988f2-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
