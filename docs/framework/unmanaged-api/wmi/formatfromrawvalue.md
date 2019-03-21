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
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue 함수
형식 변환이 시간 기반인 경우 하나의 원시 성능 데이터 값을 지정된 형식으로 변화하거나 두 개의 원시 성능 데이터 값으로 변환합니다. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

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

## <a name="parameters"></a>매개 변수

`dwCounterType`\
[in] 카운터 형식입니다. 카운터 형식 목록을 참조 하세요 [WMI 성능 카운터 형식](/windows/desktop/WmiSdk/wmi-performance-counter-types)합니다. `dwCounterType` 제외 하 고 카운터 형식일 수 있습니다 `PERF_LARGE_RAW_FRACTION` 고 `PERF_LARGE_RAW_BASE`입니다. 

`dwFormat`\
[in] 원시 성능 데이터를 변환할 대상 형식입니다. 다음 값 중 하나일 수 있습니다.

|상수  |값  |설명 |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | 배정밀도 부동 소수점 값으로 계산된 된 값을 반환 합니다. | 
| `PDH_FMT_LARGE` | 0x00000400 | 64 비트 정수로 계산된 된 값을 반환 합니다. |
| `PDH_FMT_LONG` | 0x00000100 | 32 비트 정수로 계산된 된 값을 반환 합니다. |

다음 크기 조정 플래그 중 하나를 사용 하 여 or 처리 될 수 있습니다 이전 값 중 하나:

|상수  |값  |설명 |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | 카운터의 배율 적용 되지 않습니다. |
| `PDH_FMT_1000` | 0x00002000 | 1,000 최종 값을 곱하십시오. | 

`pTimeBase`\
[in] 기본 시간을 형식으로 변환 하는 데 필요한 경우에 대 한 포인터입니다. 시간 기본 정보, 형식 변환에 대 한 필요가 없는 경우이 매개 변수의 값은 무시 됩니다.

`pRawValue1`\ [in]에 대 한 포인터를 [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) 원시 성능 값을 나타내는 구조체입니다.

`pRawValue2`\
[in] 에 대 한 포인터를 [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) 두 번째 원시 성능 값을 나타내는 구조체입니다. 두 번째 원시 성능 값이 필요한 경우이 매개 변수 여야 합니다 `null`합니다.

`pFmtValue`\
[out] 에 대 한 포인터를 [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) 구조체 형식이 지정 된 성능 값입니다.

## <a name="return-value"></a>반환 값

다음 값이이 함수에 의해 반환 됩니다.

|상수  |값  |설명  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | 함수 호출에 성공 했습니다. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | 필수 인수가 누락 되었거나 잘못 되었습니다. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | 핸들이 올바른 PDH 개체가 아닙니다. |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) 함수입니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

 **라이브러리:** PerfCounter.dll

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
