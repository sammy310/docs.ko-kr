---
title: GetFileVersion 함수
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf63b2641c4140b287a3932c2073b445211ad3aa
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490374"
---
# <a name="getfileversion-function"></a>GetFileVersion 함수
지정된 된 버퍼를 사용 하 여 지정된 된 파일의 공용 언어 런타임 (CLR) 버전 정보를 가져옵니다.  
  
 .NET Framework 4에서이 함수에 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szFilename`  
 [in] 검사할 파일의 경로입니다.  
  
 `szBuffer`  
 [out에서] 반환 되는 버전 정보에 대 한 할당 버퍼입니다.  
  
 `cchBuffer`  
 [in] 와이드 문자에서 크기의 `szBuffer`합니다.  
  
 `dwLength`  
 [out] 반환 된 바이트의 크기, `szBuffer`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
