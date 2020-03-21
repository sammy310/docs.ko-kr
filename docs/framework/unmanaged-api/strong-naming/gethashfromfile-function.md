---
title: GetHashFromFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176983"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile 함수
지정된 파일 내용에 대해 해시를 생성합니다.  
  
 이 함수는 더 이상 사용되지 않습니다. 대신 [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szFilePath`  
 【인】 해시할 파일의 이름입니다.  
  
 `piHashAlg`  
 【인, 아웃】 해시를 생성할 때 사용할 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에 의해 정의된 알고리즘입니다. 0으로 설정된 경우 `piHashAlg` 기본 알고리즘 CALG_SHA-1이 사용됩니다.  
  
 `pbHash`  
 【아웃】 생성된 해시를 포함하는 바이트 배열입니다.  
  
 `cchHash`  
 【인】 `pbHash` 가리키는 버퍼의 최대 크기입니다.  
  
 `pchHash`  
 【아웃】 반환된 `pbHash`의 크기(바이트)입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 파일 이름 사양이 유니코드 대신 ANSI라는 점을 제외하면 [GetHashFromFileW와](gethashfromfilew-function.md)동일합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetHashFromFile 메서드](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW 메서드](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
