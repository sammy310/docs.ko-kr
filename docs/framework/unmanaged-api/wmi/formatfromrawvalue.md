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
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue 함수
형식 변환이 시간 기반인 경우 하나의 원시 성능 데이터 값을 지정된 형식으로 변화하거나 두 개의 원시 성능 데이터 값으로 변환합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

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

## <a name="parameters"></a>매개 변수

`dwCounterType`\
【인】 카운터 유형입니다. 카운터 유형 목록은 [WMI 성능 카운터 유형을](/windows/desktop/WmiSdk/wmi-performance-counter-types)참조하십시오. `dwCounterType`카운터 유형이 `PERF_LARGE_RAW_FRACTION` 될 수 `PERF_LARGE_RAW_BASE`있습니다.

`dwFormat`\
【인】 원시 성능 데이터를 변환할 형식입니다. 다음 값 중 하나일 수 있습니다.

|지속적임  |값  |Description |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | 계산된 값을 이중 정밀도 부동 점 값으로 반환합니다. |
| `PDH_FMT_LARGE` | 0x00000400 | 계산된 값을 64비트 정수로 반환합니다. |
| `PDH_FMT_LONG` | 0x00000100 | 계산된 값을 32비트 정수로 반환합니다. |

이전 값 중 하나는 다음 크기 조정 플래그 중 하나를 사용할 수 있는 ORed일 수 있습니다.

|지속적임  |값  |Description |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | 카운터의 배율 계수 요소를 적용하지 마십시오. |
| `PDH_FMT_1000` | 0x00002000 | 최종 값에 1,000을 곱합니다. |

`pTimeBase`\
【인】 형식 변환에 필요한 경우 시간 기반에 대한 포인터입니다. 형식 변환에 시간 기준 정보가 필요하지 않은 경우 이 매개 변수의 값은 무시됩니다.

`pRawValue1`\
【인】 원시 성능 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 값을 나타내는 구조에 대한 포인터입니다.

`pRawValue2`\
【인】 두 번째 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 원시 성능 값을 나타내는 구조에 대한 포인터입니다. 두 번째 원시 성능 값이 필요하지 않은 `null`경우 이 매개 변수는 이 매개 변수여야 합니다.

`pFmtValue`\
【아웃】 형식이 [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) 지정된 성능 값을 받는 구조에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

다음 값은 이 함수에서 반환됩니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | 함수 호출이 성공했습니다. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | 필요한 인수가 없거나 올바르지 않습니다. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | 핸들이 유효한 PDH 개체가 아닙니다. |

## <a name="remarks"></a>설명

이 함수는 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) 함수에 대한 호출을 래핑합니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **라이브러리:** 퍼프카운터.dll

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
