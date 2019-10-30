---
title: GetHashFromHandle 함수
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140658"
---
# <a name="gethashfromhandle-function"></a>GetHashFromHandle 함수
지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hFile`  
 진행 해시할 파일의 핸들입니다.  
  
 `piHashAlg`  
 [in, out] 해시 알고리즘을 지정 하는 상수입니다. 기본 알고리즘에는 0을 사용 합니다.  
  
 `pbHash`  
 제한이 반환 된 해시 버퍼입니다.  
  
 `cchHash`  
 진행 `pbHash`요청 된 최대 크기입니다.  
  
 `pchHash`  
 제한이 반환 된 `pbHash`의 크기 (바이트)입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [GetHashFromHandle 메서드](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
