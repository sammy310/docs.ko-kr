---
title: CoInitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731753"
---
# <a name="coinitializeee-function"></a>CoInitializeEE 함수

공용 언어 런타임 실행 엔진이 프로세스로 로드 되는지 확인 합니다. 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. 대신 [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `fFlags`  
 진행 [COINITIEE](../metadata/coinitiee-enumeration.md) 열거형 상수 중 하나입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 Winerror.h에 정의 된 표준 COM 오류 코드와 다음 표에 있는 값을 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|실행 엔진이 로드 되었습니다.|  
|S_FALSE|실행 엔진이 이미 로드 되었습니다.|  
|E_FAIL|실행 엔진을 로드할 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 이전에 로드 되지 않은 경우 실행 엔진을 로드 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
