---
title: GetCORRequiredVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddb9792c00d6b78b29b66bbc3ef59ee4ad8bd81d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490409"
---
# <a name="getcorrequiredversion-function"></a>GetCORRequiredVersion 함수
필요한 공용 언어 런타임 (CLR) 버전 번호를 가져옵니다.  
  
 .NET Framework 4에서이 함수에 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbuffer`  
 [out] 버전 번호를 지정 하는 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 [in] 버퍼의 바이트 크기입니다.  
  
 `dwLength`  
 [out] 버퍼의 바이트 수를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
