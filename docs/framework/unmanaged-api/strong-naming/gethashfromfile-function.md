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
ms.openlocfilehash: ee9f9cd9a9f35c6c54497ad382bb6f9817d186bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732374"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile 함수

지정된 파일 내용에 대해 해시를 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용 합니다.  
  
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
 진행 해시할 파일의 이름입니다.  
  
 `piHashAlg`  
 [in, out] 해시를 생성할 때 사용할 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다. `piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.  
  
 `pbHash`  
 제한이 생성 된 해시를 포함 하는 바이트 배열입니다.  
  
 `cchHash`  
 진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .  
  
 `pchHash`  
 제한이 반환 된의 크기 (바이트)입니다 `pbHash` .  
  
## <a name="remarks"></a>설명  

 이 함수는 [GetHashFromFileW](gethashfromfilew-function.md)와 동일 합니다. 단, 파일 이름 사양은 유니코드가 아니라 ANSI입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [GetHashFromFile 메서드](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW 메서드](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
