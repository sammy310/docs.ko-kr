---
title: StrongNameSignatureGenerationEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
ms.openlocfilehash: e8f63a6379af8f2b7b88c511840622d49d65d587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141581"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx 함수
지정 된 플래그에 따라 지정 된 어셈블리에 대 한 강력한 이름 서명을 생성 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 진행 강력한 이름 서명이 생성 될 어셈블리의 매니페스트가 포함 된 파일의 경로입니다.  
  
 `wszKeyContainer`  
 진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.  
  
 `pbKeyBlob`가 null 인 경우에는 CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 `wszKeyContainer`. 이 경우 컨테이너에 저장 된 키 쌍을 사용 하 여 파일에 서명 합니다.  
  
 `pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.  
  
 `pbKeyBlob`  
 진행 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍은 Win32 `CryptExportKey` 함수에 의해 생성 된 형식입니다. `pbKeyBlob` null 인 경우 `wszKeyContainer`에 의해 지정 된 키 컨테이너는 키 쌍을 포함 하는 것으로 간주 됩니다.  
  
 `cbKeyBlob`  
 진행 `pbKeyBlob`의 크기 (바이트)입니다.  
  
 `ppbSignatureBlob`  
 제한이 공용 언어 런타임에서 서명을 반환 하는 위치에 대 한 포인터입니다. `ppbSignatureBlob`가 null 이면 런타임은 `wszFilePath`에 지정 된 파일에 서명을 저장 합니다.  
  
 `ppbSignatureBlob`가 null이 아닌 경우 공용 언어 런타임은 서명을 반환할 공간을 할당 합니다. 호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 공간을 확보 해야 합니다.  
  
 `pcbSignatureBlob`  
 제한이 반환 된 시그니처의 크기 (바이트)입니다.  
  
 `dwFlags`  
 진행 다음 값 중 하나 이상입니다.  
  
- `SN_SIGN_ALL_FILES` (0x00000001)-연결 된 모듈에 대 한 모든 해시를 다시 계산 합니다.  
  
- `SN_TEST_SIGN` (0x00000002)-어셈블리를 테스트 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>주의  
 서명을 만들지 않고 시그니처의 크기를 계산 하려면 `wszFilePath`에 대해 null을 지정 합니다.  
  
 시그니처는 파일에 직접 저장 되거나 호출자에 게 반환 될 수 있습니다.  
  
 `SN_SIGN_ALL_FILES` 지정 되었지만 공개 키가 포함 되지 않은 경우 (`pbKeyBlob` 및 `wszFilePath` 모두 null 임) 연결 된 모듈에 대 한 해시가 다시 계산 되지만 어셈블리는 다시 서명 되지 않습니다.  
  
 `SN_TEST_SIGN` 지정 된 경우에는 어셈블리가 강력한 이름으로 서명 되었음을 나타내는 공용 언어 런타임 헤더가 수정 되지 않습니다.  
  
 `StrongNameSignatureGenerationEx` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameSignatureGenerationEx 메서드](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration 메서드](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
