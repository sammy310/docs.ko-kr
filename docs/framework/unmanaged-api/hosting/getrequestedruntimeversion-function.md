---
description: '자세히 알아보기: GetRequestedRuntimeVersion 함수'
title: GetRequestedRuntimeVersion 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 836cc4b875ddc427c6779950f5b68d2df8b6ef75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785278"
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion 함수

지정 된 응용 프로그램에서 요청 하는 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다. 해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pExe`  
 진행 응용 프로그램의 이름입니다.  
  
 `pVersion`  
 제한이 성공적으로 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 진행 버전 버퍼의 길이입니다.  
  
 `pdwLength`  
 제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|버전 버퍼의 크기가 작아서 버전 문자열을 저장할 수 없습니다.|  
|E_POINTER|`pdwLength`가 null입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetRequestedRuntimeInfo 함수](getrequestedruntimeinfo-function.md)
- [GetVersionFromProcess 함수](getversionfromprocess-function.md)
- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
