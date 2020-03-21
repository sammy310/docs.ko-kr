---
title: StrongNameSignatureSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176892"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize 함수
강력한 이름 서명의 크기를 반환합니다. `StrongNameSignatureSize`일반적으로 지연 서명된 어셈블리를 만들 때 파일에 예약할 공간을 결정하기 위해 컴파일러에서 사용됩니다.  
  
 이 함수는 더 이상 사용되지 않습니다. 대신 [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `pbPublicKeyBlob`  
 【인】 강력한 이름 서명을 생성하는 데 사용되는 키 쌍의 공용 부분을 포함하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조입니다.  
  
 `cbPublicKeyBlob`  
 【인】 의 크기(바이트)입니다. `pbPublicKeyBlob`  
  
 `pcbSize`  
 【인】 강력한 이름 서명을 저장하는 데 필요한 바이트 수입니다.  
  
## <a name="return-value"></a>Return Value  
 `true`성공적인 완료시; 그렇지 `false`않으면 .  
  
## <a name="remarks"></a>설명  
 `StrongNameSignatureSize`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameSignatureSize 메서드](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
