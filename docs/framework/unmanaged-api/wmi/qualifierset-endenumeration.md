---
title: QualifierSet_EndEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_EndEnumeration 함수 열거형을 종료합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2dfd6bb521dee14afd3728bdd9c446cb779e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598846"
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration 함수
에 대 한 호출으로 시작 하는 열거형을 종료 합니다 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`   
[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 되어는 *WbemCli.h* 헤더 파일을 정의할 수는 상수로 코드에서:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) 메서드.

이 호출은 것이 좋지만 필요 하지 않습니다. 열거형을 사용 하 여 연결 된 리소스를 즉시 해제 합니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
**헤더:** WMINet_Utils.idl  
  
**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
