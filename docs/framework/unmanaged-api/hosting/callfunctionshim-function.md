---
description: '자세한 정보: CallFunctionShim 함수'
title: CallFunctionShim 함수
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: 7ddd16a06005011adcf41190929fd62f4132f14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799956"
---
# <a name="callfunctionshim-function"></a>CallFunctionShim 함수

지정 된 라이브러리에서 지정 된 이름 및 매개 변수를 가진 함수를 호출 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szDllName`  
 진행 함수를 포함 하는 라이브러리의 이름입니다.  
  
 `szFunctionName`  
 진행 함수의 이름입니다.  
  
 `lpvArgument1`  
 진행 함수에 전달할 첫 번째 인수입니다.  
  
 `lpvArgument2`  
 진행 함수에 전달할 두 번째 인수입니다.  
  
 `szVersion`  
 진행 함수를 포함 하는 라이브러리의 버전입니다.  
  
 `pvReserved`  
 진행 나중에 사용 하도록 예약 되어 있습니다. 이 매개 변수에서 0을 전달 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
