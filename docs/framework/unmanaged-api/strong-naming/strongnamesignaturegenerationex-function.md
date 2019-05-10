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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 059dadcaf7a55074e30c59873a8c1e7016b0a33e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666001"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx 함수
지정된 된 플래그에 따라 지정된 된 어셈블리의 강력한 이름 시그니처를 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnamesignaturegenerationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
 [in] 강력한 이름 시그니처를 생성 하는 어셈블리의 매니페스트가 포함 된 파일 경로입니다.  
  
 `wszKeyContainer`  
 [in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.  
  
 하는 경우 `pbKeyBlob` 이 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다. 이 경우 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.  
  
 경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.  
  
 `pbKeyBlob`  
 [in] 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍이 win32 만들어진 형식을 `CryptExportKey` 함수입니다. 하는 경우 `pbKeyBlob` 가 null 이면 지정 된 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하도록 간주 됩니다.  
  
 `cbKeyBlob`  
 [in] 크기 (바이트)의 `pbKeyBlob`합니다.  
  
 `ppbSignatureBlob`  
 [out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다. 하는 경우 `ppbSignatureBlob` 가 null 이면 런타임에서 서명을 저장 하 여 지정한 파일에 `wszFilePath`입니다.  
  
 경우 `ppbSignatureBlob` 는 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다. 호출자에 게 사용 하 여이 공간을 해제 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.  
  
 `pcbSignatureBlob`  
 [out] 반환 된 서명의 바이트 크기입니다.  
  
 `dwFlags`  
 [in] 하나 이상의 다음 값 중:  
  
- `SN_SIGN_ALL_FILES` (0x00000001)-연결 된 모듈에 대 한 모든 해시를 다시 계산 합니다.  
  
- `SN_TEST_SIGN` (0x00000002)-테스트-어셈블리를 서명 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명의 크기를 계산 합니다.  
  
 서명 될 파일에 직접 저장 하거나 호출자에 게 반환 합니다.  
  
 경우 `SN_SIGN_ALL_FILES` 지정 된 공개 키 포함 되지 않습니다. 하지만 (둘 다 `pbKeyBlob` 및 `wszFilePath` null), 연결 된 모듈에 대 한 해시를 다시 계산할지를 아닌 어셈블리 다시 서명 합니다.  
  
 경우 `SN_TEST_SIGN` 지정 된 경우 공용 언어 런타임 헤더는 강력한 이름으로 어셈블리 서명 되었음을 나타내도록 수정 되지 않습니다.  
  
 경우는 `StrongNameSignatureGenerationEx` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [StrongNameSignatureGenerationEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
