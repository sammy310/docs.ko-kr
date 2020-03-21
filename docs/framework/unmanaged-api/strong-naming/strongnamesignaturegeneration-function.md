---
title: StrongNameSignatureGeneration 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176905"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration 함수
지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.  
  
 이 함수는 더 이상 사용되지 않습니다. 대신 [ICLRStrongName::강력한 이름 서명 생성](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 【인】 강력한 이름 서명이 생성되는 어셈블리의 매니페스트가 포함된 파일의 경로입니다.  
  
 `wszKeyContainer`  
 【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.  
  
 null인 `pbKeyBlob` `wszKeyContainer` 경우 CSP(암호화 서비스 공급자) 내에서 유효한 컨테이너를 지정해야 합니다. 이 경우 컨테이너에 저장된 키 쌍이 파일에 서명하는 데 사용됩니다.  
  
 null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.  
  
 키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다. 현재 다른 유형의 키는 지원되지 않습니다.  
  
 `pbKeyBlob`  
 【인】 공용/개인 키 쌍에 대한 포인터입니다. 이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다. null인 경우 `pbKeyBlob` 지정한 `wszKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.  
  
 `cbKeyBlob`  
 【인】 의 크기(바이트)입니다. `pbKeyBlob`  
  
 `ppbSignatureBlob`  
 【아웃】 공통 언어 런타임이 서명을 반환하는 위치에 대한 포인터입니다. null인 경우 `ppbSignatureBlob` 런타임은 에 의해 지정된 `wszFilePath`파일에 서명을 저장합니다.  
  
 null이 아닌 경우 `ppbSignatureBlob` 공통 언어 런타임은 서명을 반환할 공간을 할당합니다. 호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용하여 이 공간을 확보해야 합니다.  
  
 `pcbSignatureBlob`  
 【아웃】 반환된 서명의 크기(바이트)입니다.  
  
## <a name="return-value"></a>Return Value  
 `true`성공적인 완료시; 그렇지 `false`않으면 .  
  
## <a name="remarks"></a>설명  
 서명을 만들지 `wszFilePath` 않고 서명 크기를 계산하려면 null을 지정합니다.  
  
 서명을 파일에 직접 저장하거나 호출자에게 반환할 수 있습니다.  
  
 `StrongNameSignatureGeneration`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameSignatureGeneration 메서드](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [StrongNameSignatureGenerationEx 메서드](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
