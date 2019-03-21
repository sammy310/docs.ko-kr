---
title: FormatFromRawValue 함수 (관리 되지 않는 API 참조)
description: FormatFromRawValue 함수는 지정 된 형식 원시 성능 데이터를 변환합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a84b03c85cc1332c07ffbaf53187b7f01d0236
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262464"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="8547d-103">FormatFromRawValue 함수</span><span class="sxs-lookup"><span data-stu-id="8547d-103">FormatFromRawValue function</span></span>
<span data-ttu-id="8547d-104">형식 변환이 시간 기반인 경우 하나의 원시 성능 데이터 값을 지정된 형식으로 변화하거나 두 개의 원시 성능 데이터 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8547d-105">구문</span><span class="sxs-lookup"><span data-stu-id="8547d-105">Syntax</span></span>

```
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```

## <a name="parameters"></a><span data-ttu-id="8547d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8547d-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="8547d-107">[in] 카운터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-107">[in] The counter type.</span></span> <span data-ttu-id="8547d-108">카운터 형식 목록을 참조 하세요 [WMI 성능 카운터 형식](/windows/desktop/WmiSdk/wmi-performance-counter-types)합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="8547d-109">`dwCounterType` 제외 하 고 카운터 형식일 수 있습니다 `PERF_LARGE_RAW_FRACTION` 고 `PERF_LARGE_RAW_BASE`입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="8547d-110">[in] 원시 성능 데이터를 변환할 대상 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="8547d-111">다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-111">It can be one of the following values:</span></span>

|<span data-ttu-id="8547d-112">상수</span><span class="sxs-lookup"><span data-stu-id="8547d-112">Constant</span></span>  |<span data-ttu-id="8547d-113">값</span><span class="sxs-lookup"><span data-stu-id="8547d-113">Value</span></span>  |<span data-ttu-id="8547d-114">설명</span><span class="sxs-lookup"><span data-stu-id="8547d-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="8547d-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="8547d-115">0x00000200</span></span> | <span data-ttu-id="8547d-116">배정밀도 부동 소수점 값으로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="8547d-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="8547d-117">0x00000400</span></span> | <span data-ttu-id="8547d-118">64 비트 정수로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="8547d-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="8547d-119">0x00000100</span></span> | <span data-ttu-id="8547d-120">32 비트 정수로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="8547d-121">다음 크기 조정 플래그 중 하나를 사용 하 여 or 처리 될 수 있습니다 이전 값 중 하나:</span><span class="sxs-lookup"><span data-stu-id="8547d-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="8547d-122">상수</span><span class="sxs-lookup"><span data-stu-id="8547d-122">Constant</span></span>  |<span data-ttu-id="8547d-123">값</span><span class="sxs-lookup"><span data-stu-id="8547d-123">Value</span></span>  |<span data-ttu-id="8547d-124">설명</span><span class="sxs-lookup"><span data-stu-id="8547d-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="8547d-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="8547d-125">0x00001000</span></span> | <span data-ttu-id="8547d-126">카운터의 배율 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="8547d-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="8547d-127">0x00002000</span></span> | <span data-ttu-id="8547d-128">1,000 최종 값을 곱하십시오.</span><span class="sxs-lookup"><span data-stu-id="8547d-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="8547d-129">[in] 기본 시간을 형식으로 변환 하는 데 필요한 경우에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="8547d-130">시간 기본 정보, 형식 변환에 대 한 필요가 없는 경우이 매개 변수의 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="8547d-131">`pRawValue1`\ [in]에 대 한 포인터를 [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) 원시 성능 값을 나타내는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="8547d-132">[in] 에 대 한 포인터를 [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) 두 번째 원시 성능 값을 나타내는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="8547d-133">두 번째 원시 성능 값이 필요한 경우이 매개 변수 여야 합니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="8547d-134">[out] 에 대 한 포인터를 [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) 구조체 형식이 지정 된 성능 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="8547d-135">반환 값</span><span class="sxs-lookup"><span data-stu-id="8547d-135">Return value</span></span>

<span data-ttu-id="8547d-136">다음 값이이 함수에 의해 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="8547d-137">상수</span><span class="sxs-lookup"><span data-stu-id="8547d-137">Constant</span></span>  |<span data-ttu-id="8547d-138">값</span><span class="sxs-lookup"><span data-stu-id="8547d-138">Value</span></span>  |<span data-ttu-id="8547d-139">설명</span><span class="sxs-lookup"><span data-stu-id="8547d-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="8547d-140">0</span><span class="sxs-lookup"><span data-stu-id="8547d-140">0</span></span> | <span data-ttu-id="8547d-141">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="8547d-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="8547d-142">0xC0000BBD</span></span> | <span data-ttu-id="8547d-143">필수 인수가 누락 되었거나 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="8547d-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="8547d-144">0xC0000BBC</span></span> | <span data-ttu-id="8547d-145">핸들이 올바른 PDH 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8547d-146">설명</span><span class="sxs-lookup"><span data-stu-id="8547d-146">Remarks</span></span>

<span data-ttu-id="8547d-147">이 함수에 대 한 호출을 래핑하는 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8547d-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8547d-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8547d-148">Requirements</span></span>

 <span data-ttu-id="8547d-149">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8547d-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8547d-150">**라이브러리:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="8547d-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="8547d-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8547d-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8547d-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="8547d-152">See also</span></span>

- [<span data-ttu-id="8547d-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="8547d-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
