---
title: StrongNameSignatureVerificationFromImage 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54b1d35d1c40289bad465978750ba738acf28c90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212442"
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage 함수
메모리에 이미 매핑된 어셈블리가 연결된 공개 키에 유효한지 확인합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbBase`  
 [in] 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.  
  
 `dwLength`  
 [in] 매핑된 이미지의 바이트 크기입니다.  
  
 `dwInFlags`  
 [in] 확인 동작에 영향을 주는 플래그입니다. 다음 값이 지원 됩니다.  
  
-   `SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에 확인이 수행 합니다.  
  
-   `SN_INFLAG_INSTALL` (0x00000002)-이 이미지에서 수행 된 첫 번째 확인 작업 임을 지정 합니다.  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시는 관리 권한이 있는 사용자만 액세스할 수 있도록 지정 합니다.  
  
-   `SN_INFLAG_USER_ACCESS` (0x00000008)-어셈블리는 현재 사용자만 액세스할 수 있도록 지정 합니다.  
  
-   `SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.  
  
-   `SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅을 위해 예약 되어 있습니다.  
  
 `pdwOutFlags`  
 [out] 출력 추가 정보에 대 한 플래그입니다. 다음 값을 사용할 수 있습니다.  
  
-   `SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값 설정할지 `false` 레지스트리 설정으로 인해 확인이 성공 했는지를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 경우는 `StrongNameSignatureVerificationFromImage` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [StrongNameSignatureVerificationFromImage 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
